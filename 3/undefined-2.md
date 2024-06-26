# 크로스 플랫폼 앱 만들기

여기에서는 Android Studio를 사용하여 첫 번째 Kotlin 다중 플랫폼 애플리케이션을 만들고 실행하는 방법을 알아봅니다.

### 마법사를 사용하여 프로젝트 만들기﻿ <a href="#create-the-project-with-a-wizard" id="create-the-project-with-a-wizard"></a>

1. [Kotlin 다중 플랫폼 마법사를](https://kmp.jetbrains.com/) 엽니다 .
2. 새 프로젝트 탭 에서 프로젝트 이름을 "GreetingKMP"로, 프로젝트 ID를 "com.jetbrains.greeting"으로 변경합니다.
3. Android 및 iOS 옵션이 선택되어 있는지 확인하세요 .
4. iOS의 경우 UI를 기본으로 유지하려면 UI 공유 안 함 옵션을 선택하세요.
5. 다운로드 버튼을 클릭 하고 결과 아카이브의 압축을 풉니다.

<figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/multiplatform-web-wizard-1.png" alt="Kotlin 다중 플랫폼 마법사" height="674" width="450"><figcaption></figcaption></figure>

### 프로젝트 구조 검토﻿ <a href="#examine-the-project-structure" id="examine-the-project-structure"></a>

1. 안드로이드 스튜디오를 실행하세요.
2. 시작 화면에서 열기를 클릭 하거나 파일 | 편집기에서 엽니다 .
3.  압축을 푼 프로젝트 폴더로 이동한 다음 열기 를 클릭합니다 .

    Android Studio는 폴더에 Gradle 빌드 파일이 포함되어 있음을 감지하고 해당 폴더를 새 프로젝트로 엽니다.
4.  Android Studio의 기본 뷰는 Android 개발에 최적화되어 있습니다. 멀티플랫폼 개발에 더 편리한 프로젝트의 전체 파일 구조를 보려면 Android 에서 Project 로 뷰를 전환합니다 .

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/select-project-view.png" alt="프로젝트 보기 선택" height="308" width="200"><figcaption></figcaption></figure>

각 Kotlin Multiplatform 프로젝트에는 세 가지 모듈이 포함됩니다.

* _shared는_ Android와 iOS 애플리케이션 모두에 공통적인 로직, 즉 플랫폼 간에 공유하는 코드를 포함하는 Kotlin 모듈입니다. [Gradle을](https://kotlinlang.org/docs/gradle.html) 빌드 시스템으로 사용하여 빌드 프로세스를 자동화합니다.
* _composeApp은_ Android 애플리케이션에 빌드되는 Kotlin 모듈입니다. Gradle을 빌드 시스템으로 사용합니다. composeApp 모듈은 공유 모듈을 일반 Android 라이브러리로 의존하고 사용합니다.
* _iosApp은_ iOS 애플리케이션에 빌드되는 Xcode 프로젝트입니다. iOS 프레임워크로 공유 모듈에 의존하고 사용합니다. 공유 모듈은 일반 프레임워크 또는 [CocoaPods 종속성](https://kotlinlang.org/docs/native-cocoapods.html) 으로 사용될 수 있습니다 . 기본적으로 Kotlin 다중 플랫폼 마법사는 일반 프레임워크 종속성을 사용하는 프로젝트를 생성합니다.

<figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/basic-project-structure.svg" alt="기본 멀티플랫폼 프로젝트 구조" height="700" width="700"><figcaption></figcaption></figure>

공유 모듈은 , 및 의 세 가지 소스 세트로 `androidMain`구성 `commonMain`됩니다 `iosMain`. _소스 세트_ 는 각 그룹이 자체 종속성을 갖는 논리적으로 함께 그룹화된 여러 파일에 대한 Gradle 개념입니다. Kotlin Multiplatform에서는 공유 모듈의 다양한 소스 세트가 다양한 플랫폼을 대상으로 할 수 있습니다.

공통 소스 세트에는 공유 Kotlin 코드가 포함되어 있으며 플랫폼 소스 세트는 각 대상에 특정한 Kotlin 코드를 사용합니다. Kotlin/JVM은 다음 용도로 사용되며 `androidMain`Kotlin/Native는 다음 용도로 사용됩니다 `iosMain`.

<figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/basic-project-structure-2.png" alt="소스 세트 및 모듈 구조" height="311" width="200"><figcaption></figcaption></figure>

공유 모듈이 Android 라이브러리에 내장되면 일반적인 Kotlin 코드는 Kotlin/JVM으로 처리됩니다. iOS 프레임워크에 내장되면 일반적인 Kotlin은 Kotlin/Native로 처리됩니다.

<figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/modules-structure.png" alt="공통 Kotlin, Kotlin/JVM 및 Kotlin/Native" height="193" width="694"><figcaption></figcaption></figure>

#### 공통 선언 작성﻿ <a href="#write-common-declarations" id="write-common-declarations"></a>

공통 소스 세트에는 여러 대상 플랫폼에서 사용할 수 있는 공유 코드가 포함되어 있습니다. 플랫폼 독립적인 코드를 포함하도록 설계되었습니다. 공통 소스 세트에서 플랫폼별 API를 사용하려고 하면 IDE에 다음과 같은 경고가 표시됩니다.

1.  파일을 열고 함수 내에서 `Greeting.kt`Java 클래스 중 하나에 액세스해 보십시오 .`java.util.Random().nextBoolean()greet()`

    ```
    import java.util.Random

    fun greet(): String {
        val firstWord = if (Random().nextBoolean()) "Hi!" else "Hello!"

        return firstWord
    }
    ```

    Android 스튜디오에서는 `Random`일반 Kotlin 코드에서 특정 자바 함수를 호출할 수 없기 때문에 클래스가 확인되지 않았음을 강조합니다.
2. IDE의 제안을 따르고 이를 `kotlin.random.Random`Kotlin 표준 라이브러리의 라이브러리로 바꾸세요. 이는 모든 플랫폼에서 작동하며 자동으로 종속성으로 포함되는 다중 플랫폼 라이브러리입니다.
3. `Random()`추상 클래스이므로 에서 대괄호를 제거하세요 . 이제 코드가 성공적으로 컴파일됩니다.
4.  인사말에 다양성을 더해보세요. `reversed()`텍스트를 반전하려면 Kotlin 표준 라이브러리의 함수 로 공유 코드를 업데이트하세요 .

    ```
    import kotlin.random.Random

    class Greeting {
        private val platform: Platform = getPlatform()

        fun greet(): String {
            val firstWord = if (Random.nextBoolean()) "Hi!" else "Hello!"

            return "$firstWord Guess what this is! > ${platform.name.reversed()}!"
        }
    }
    ```

일반적인 Kotlin으로만 코드를 작성하면 특정 플랫폼을 사용할 수 없기 때문에 분명한 한계가 있습니다. 인터페이스와 [예상/실제](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-connect-to-apis.html) 메커니즘을 사용하면 이 문제가 해결됩니다.

#### 플랫폼별 구현을 확인하세요.﻿ <a href="#check-out-platform-specific-implementations" id="check-out-platform-specific-implementations"></a>

공통 소스 세트는 인터페이스 또는 예상 선언을 정의할 수 있습니다. 그런 다음 각 플랫폼 소스 세트(이 경우 `androidMain`및 `iosMain`)는 공통 소스 세트의 예상 선언에 대한 실제 플랫폼별 구현을 제공해야 합니다.

특정 플랫폼에 대한 코드를 생성하는 동안 Kotlin 컴파일러는 예상 선언과 실제 선언을 병합하고 실제 구현이 포함된 단일 선언을 생성합니다.

1.  웹 마법사를 사용하거나 Android 스튜디오에서 Kotlin Multiplatform 플러그인을 사용하여 프로젝트를 생성하면 모듈 `Platform.kt`의 파일이 포함된 템플릿을 얻게 됩니다 `commonMain`.

    ```
    interface Platform {
        val name: String
    }
    ```

    `Platform`플랫폼에 대한 정보가 포함된 공통 인터페이스입니다 .
2.  `androidMain`및 모듈 간을 전환합니다 `iosMain`. Android 및 iOS 소스 세트에 대해 동일한 기능을 다르게 구현한 것을 확인할 수 있습니다.

    ```
    // Platform.android.kt in the androidMain module:
    class AndroidPlatform: Platform {
        override val name: String =
            "Android ${android.os.Build.VERSION.SDK_INT}"
    }
    ```

    ```
    // Platform.ios.kt in the iosMain module:
    import platform.UIKit.UIDevice

    class IOSPlatform: Platform {
        override val name: String =
            UIDevice.currentDevice.systemName() + " " + UIDevice.currentDevice.systemVersion
    }
    ```

    * 속성 `name`구현은 `AndroidPlatform`Android 플랫폼 코드, 즉 `android.os.Build`종속성을 사용합니다. 이 코드는 Kotlin/JVM으로 작성되었습니다. 여기에 접근하려고 하면 `java.util.Random`이 코드가 컴파일됩니다.
    * 속성 `name`구현은 `IOSPlatform`iOS 플랫폼 코드, 즉 `platform.UIKit.UIDevice`종속성을 사용합니다. Kotlin/Native로 작성되었습니다. 즉, Kotlin으로 iOS 코드를 작성할 수 있습니다. 이 코드는 나중에 iOS 애플리케이션의 Swift에서 호출하게 될 iOS 프레임워크의 일부가 됩니다.
3.  `getPlatform()`다양한 소스 세트에서 기능을 확인하세요 . 예상되는 선언에는 본문이 없으며 실제 구현은 플랫폼 코드에서 제공됩니다.

    ```
    // Platform.kt in the commonMain module:
    expect fun getPlatform(): Platform
    ```

    ```
    // Platform.android.kt in the androidMain module:
    actual fun getPlatform(): Platform = AndroidPlatform()
    ```

    ```
    // Platform.ios.kt in the iosMain module:
    actual fun getPlatform(): Platform = IOSPlatform()
    ```

여기서 공통 소스 세트는 예상되는 기능을 정의 하고 플랫폼 소스 세트에서 Android 앱 및 iOS 앱에 대한 `getPlatform()`실제 구현을 갖습니다 .`AndroidPlatform()IOSPlatform()`

특정 플랫폼에 대한 코드를 생성하는 동안 Kotlin 컴파일러는 예상 선언과 실제 선언을 `getPlatform()`실제 구현과 함께 단일 함수로 병합합니다.

이것이 바로 예상 선언과 실제 선언이 동일한 패키지에 정의되어야 하는 이유입니다. 즉, 결과 플랫폼 코드에서 하나의 선언으로 병합됩니다. `getPlatform()`생성된 플랫폼 코드에서 예상되는 기능을 호출하면 올바른 실제 구현이 호출됩니다.

이제 앱을 실행하고 이 모든 것이 실제로 작동하는 것을 볼 수 있습니다.

**예상/실제 메커니즘 살펴보기(선택 사항)**﻿

1. ```
   ```
2. ```
   ```
3. ```
   ```
4. ```
   ```
5. ```
   ```

### 애플리케이션 실행﻿ <a href="#run-your-application" id="run-your-application"></a>

Android Studio에서 [Android](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-create-first-app.html#run-your-application-on-android) 또는 [iOS](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-create-first-app.html#run-your-application-on-ios) 용 다중 플랫폼 애플리케이션을 실행할 수 있습니다 .

#### Android에서 애플리케이션 실행﻿ <a href="#run-your-application-on-android" id="run-your-application-on-android"></a>

1. 실행 구성 목록에서 composeApp 을 선택합니다 .
2.  구성 목록 옆에 있는 Android 가상 기기를 선택하고 실행을 클릭합니다 .

    목록에 기기가 없으면 [새 Android 가상 기기를](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-create-first-app.html#run-on-a-new-ios-simulated-device) 만듭니다 .

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/compose-run-android.png" alt="Android에서 다중 플랫폼 앱 실행" height="40" width="400"><figcaption></figcaption></figure>

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/first-multiplatform-project-on-android-1.png" alt="Android 최초의 모바일 다중 플랫폼 앱" height="631" width="300"><figcaption></figcaption></figure>

**다른 Android 시뮬레이션 기기에서 실행**﻿



**실제 Android 기기에서 실행**﻿



#### iOS에서 애플리케이션 실행﻿ <a href="#run-your-application-on-ios" id="run-your-application-on-ios"></a>

1. 별도의 창에서 Xcode를 실행합니다. 이 작업을 처음 수행하는 경우 라이센스 조건에 동의하고 Xcode가 필요한 초기 작업을 수행하도록 허용해야 할 수도 있습니다.
2.  Android Studio의 실행 구성 목록에서 iosApp을 선택하고 Run을 클릭합니다 .

    목록에 사용 가능한 iOS 구성이 없으면 [새로운 실행 구성을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-create-first-app.html#run-on-a-new-ios-simulated-device) 추가하세요 .

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/compose-run-ios.png" alt="iOS에서 멀티플랫폼 앱 실행" height="50" width="450"><figcaption></figcaption></figure>

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/first-multiplatform-project-on-ios-1.png" alt="iOS 최초의 모바일 멀티플랫폼 앱" height="593" width="300"><figcaption></figcaption></figure>

**새로운 iOS 시뮬레이션 장치에서 실행**﻿

1.

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/ios-edit-configurations.png" alt="실행 구성 편집" height="176" width="450"><figcaption></figcaption></figure>
2.

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/ios-new-configuration.png" alt="iOS 애플리케이션을 위한 새로운 실행 구성" height="1388" width="2062"><figcaption></figcaption></figure>
3.
4.
5.

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/ios-new-simulator.png" alt="iOS 시뮬레이터를 사용한 새로운 실행 구성" height="1050" width="1686"><figcaption></figcaption></figure>
6.

**실제 iOS 기기에서 실행**﻿
