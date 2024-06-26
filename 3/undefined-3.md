# 종속성 추가

이미 첫 번째 크로스 플랫폼 Kotlin Multiplatform 프로젝트를 만들었습니다! 이제 성공적인 크로스 플랫폼 애플리케이션을 구축하는 데 필요한 타사 라이브러리에 종속성을 추가하는 방법을 알아 보겠습니다.

### 종속성 유형﻿ <a href="#dependency-types" id="dependency-types"></a>

Kotlin 다중 플랫폼 프로젝트에서 사용할 수 있는 종속 항목에는 두 가지 유형이 있습니다.

*   _다중 플랫폼 종속성_ . 이는 여러 대상을 지원하고 공통 소스 세트인 `commonMain`.

    많은 최신 Android 라이브러리에는 이미 [Koin](https://insert-koin.io/) , [Apollo](https://www.apollographql.com/) 및 [Okio](https://square.github.io/okio/) 와 같은 다중 플랫폼이 지원됩니다 .
*   _기본 종속성_ . 관련 생태계의 일반 라이브러리입니다. 네이티브 프로젝트에서는 일반적으로 Android용 Gradle을 사용하고 CocoaPods 또는 iOS용 다른 종속성 관리자를 사용하여 작업합니다.

    공유 모듈로 작업할 때 일반적으로 보안 저장소와 같은 플랫폼 API를 사용하려는 경우 기본 종속성이 여전히 필요합니다. 네이티브 소스 세트에 네이티브 종속성을 추가할 수 `androidMain`있으며 `iosMain`.

두 가지 유형의 종속성에 대해 로컬 및 외부 저장소를 사용할 수 있습니다.

### 다중 플랫폼 종속성 추가﻿ <a href="#add-a-multiplatform-dependency" id="add-a-multiplatform-dependency"></a>

> ####
>
> Android 앱 개발 경험이 있는 경우 다중 플랫폼 종속성을 추가하는 것은 일반 Android 프로젝트에 Gradle 종속성을 추가하는 것과 유사합니다. 유일한 차이점은 소스 세트를 지정해야 한다는 것입니다.

앱으로 돌아가서 인사말을 좀 더 축제적으로 만들어 보겠습니다. 기기 정보 외에 설날까지 남은 일수를 표시하는 기능을 추가합니다. 멀티플랫폼을 완벽하게 지원하는 라이브러리 `kotlinx-datetime`는 공유 코드에서 날짜를 처리하는 가장 편리한 방법입니다.

1. `build.gradle.kts`디렉토리 에 있는 파일을 엽니다 `shared`.
2.  소스 세트 종속성 에 다음 종속성을 추가합니다 `commonMain`.

    ```
    kotlin {
        sourceSets {
            commonMain.dependencies {
                implementation("org.jetbrains.kotlinx:kotlinx-datetime:0.4.0")
            }
        }
    }
    ```
3.  알림에서 지금 동기화를 클릭하여 Gradle 파일을 동기화합니다 .

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/gradle-sync.png" alt="Gradle 파일 동기화" height="78" width="1570"><figcaption></figcaption></figure>
4. 에서 프로젝트 디렉터리에 `shared/src/commonMain/kotlin`새 파일을 만듭니다 .`NewYear.kt`
5.  날짜 산술을 사용하여 오늘부터 새해까지의 일수를 계산하는 간단한 함수로 파일을 업데이트합니다 `date-time`.

    ```
    import kotlinx.datetime.*

    fun daysUntilNewYear(): Int {
        val today = Clock.System.todayIn(TimeZone.currentSystemDefault())
        val closestNewYear = LocalDate(today.year + 1, 1, 1)
        return today.daysUntil(closestNewYear)
    }

    fun daysPhrase(): String = "There are only ${daysUntilNewYear()} days left until New Year! 🎆"
    ```
6.  에서 클래스를 `Greeting.kt`업데이트하여 `Greeting`결과를 확인합니다.

    ```
    class Greeting {
        private val platform: Platform = getPlatform()

        fun greet(): List<String> = buildList {
            add(if (Random.nextBoolean()) "Hi!" else "Hello!")
            add("Guess what this is! > ${platform.name.reversed()}!")
            add(daysPhrase())
        }
    }
    ```
7. 결과를 보려면 Android Studio에서 composeApp 및 iosApp 구성을 다시 실행하세요.

<figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/first-multiplatform-project-3.png" alt="외부 종속성을 갖춘 업데이트된 모바일 다중 플랫폼 앱" height="513" width="500"><figcaption></figcaption></figure>

### 다음 단계﻿ <a href="#next-step" id="next-step"></a>

자습서의 다음 부분에서는 프로젝트에 더 많은 종속성과 더 복잡한 논리를 추가합니다.

[다음 부분으로 진행](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-upgrade-app.html)

#### 또한보십시오﻿ <a href="#see-also" id="see-also"></a>

* [Kotlin 라이브러리, Kotlin 다중 플랫폼 라이브러리, 기타 다중 플랫폼 프로젝트 등](https://kotlinlang.org/docs/multiplatform-add-dependencies.html) 모든 종류의 다중 플랫폼 종속성을 사용하는 방법을 알아보세요 .
* 플랫폼별 소스 세트에서 사용하기 위해 [CocoaPods를 사용하거나 사용하지 않고 ](https://kotlinlang.org/docs/multiplatform-ios-dependencies.html)[Android 종속성](https://kotlinlang.org/docs/multiplatform-android-dependencies.html) 과 iOS 종속성을 추가하는 방법을 알아보세요 .
* 샘플 프로젝트에서 [Android 및 iOS 라이브러리를 사용하는 방법](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-samples.html) 에 대한 예제를 확인하세요 .
