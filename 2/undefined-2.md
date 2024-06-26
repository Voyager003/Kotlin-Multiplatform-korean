# 자주하는 질문

### Kotlin 멀티플랫폼﻿ <a href="#kotlin-multiplatform" id="kotlin-multiplatform"></a>

#### Kotlin 멀티플랫폼이란 무엇인가요?﻿ <a href="#what-is-kotlin-multiplatform" id="what-is-kotlin-multiplatform"></a>

[KMP( Kotlin Multiplatform](https://www.jetbrains.com/kotlin-multiplatform/) )는 유연한 크로스 플랫폼 개발을 위한 JetBrains의 오픈 소스 기술입니다. 이를 통해 다양한 플랫폼용 애플리케이션을 만들고 네이티브 프로그래밍의 이점을 유지하면서 코드를 효율적으로 재사용할 수 있습니다. Kotlin Multiplatform을 사용하면 Android, iOS, 데스크톱, 웹, 서버 측 및 기타 플랫폼용 앱을 개발할 수 있습니다.

#### Kotlin Multiplatform과 UI를 공유할 수 있나요?﻿ <a href="#can-i-share-uis-with-kotlin-multiplatform" id="can-i-share-uis-with-kotlin-multiplatform"></a>

[예, Kotlin 및 Jetpack Compose를](https://developer.android.com/jetpack/compose) 기반으로 하는 JetBrains의 선언적 UI 프레임워크 인 [Compose Multiplatform](https://www.jetbrains.com/lp/compose-multiplatform/) 을 사용하여 UI를 공유할 수 있습니다 . 이 프레임워크를 사용하면 iOS, Android, 데스크톱, 웹과 같은 플랫폼용 공유 UI 구성 요소를 생성하여 다양한 장치와 플랫폼에서 일관된 사용자 인터페이스를 유지할 수 있습니다.

자세한 내용은 [Compose 다중 플랫폼](https://www.jetbrains.com/help/kotlin-multiplatform-dev/faq.html#compose-multiplatform) 섹션을 참조하세요.

#### Kotlin Multiplatform은 어떤 플랫폼을 지원하나요?﻿ <a href="#what-platforms-does-kotlin-multiplatform-support" id="what-platforms-does-kotlin-multiplatform-support"></a>

Kotlin Multiplatform은 Android, iOS, 데스크톱, 웹, 서버 측 및 기타 플랫폼을 지원합니다. [지원되는 플랫폼](https://www.jetbrains.com/help/kotlin-multiplatform-dev/supported-platforms.html) 에 대해 자세히 알아보세요 .

#### 크로스 플랫폼 앱은 어떤 IDE에서 작업해야 합니까?﻿ <a href="#in-which-ide-should-i-work-on-my-cross-platform-app" id="in-which-ide-should-i-work-on-my-cross-platform-app"></a>

프로젝트 요구사항과 기대치에 따라 JetBrains Fleet 코드 편집기 또는 Android Studio IDE를 사용하는 것이 좋습니다. [권장 IDE 및 코드 편집기](https://www.jetbrains.com/help/kotlin-multiplatform-dev/recommended-ides.html) 에서 어떤 것을 선택할지 자세히 알아보세요 .

#### 새로운 Kotlin Multiplatform 프로젝트를 만들려면 어떻게 해야 하나요?﻿ <a href="#how-do-i-create-a-new-kotlin-multiplatform-project" id="how-do-i-create-a-new-kotlin-multiplatform-project"></a>

[Kotlin 다중 플랫폼 시작하기](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-getting-started.html) 튜토리얼은 Kotlin 다중 플랫폼 프로젝트 생성을 위한 단계별 지침을 제공합니다. 로직만 공유할지, 로직과 UI를 모두 공유할지 결정할 수 있습니다.

#### 기존 Android 애플리케이션이 있습니다. Kotlin Multiplatform으로 마이그레이션하려면 어떻게 해야 하나요?﻿ <a href="#i-have-an-existing-android-application-how-can-i-migrate-it-to-kotlin-multiplatform" id="i-have-an-existing-android-application-how-can-i-migrate-it-to-kotlin-multiplatform"></a>

[iOS에서 Android 애플리케이션이 작동하도록 만드는](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-integrate-in-existing-app.html) 단계별 튜토리얼에서는 기본 UI를 사용하여 Android 애플리케이션이 iOS에서 작동하도록 만드는 방법을 설명합니다. Compose Multiplatform과 UI를 공유하려면 [해당 답변을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/faq.html#i-have-an-existing-android-application-that-uses-jetpack-compose-what-should-i-do-to-migrate-it-to-other-platforms) 참조하세요 .

#### 완전한 예제를 어디에서 얻을 수 있나요?﻿ <a href="#where-can-i-get-complete-examples-to-play-with" id="where-can-i-get-complete-examples-to-play-with"></a>

다음은 [실제 사례 목록](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-samples.html) 입니다 .

#### 실제 Kotlin Multiplatform 애플리케이션 목록은 어디에서 찾을 수 있나요? 어떤 회사가 생산에 KMP를 사용합니까?﻿ <a href="#where-can-i-find-a-list-of-real-life-kotlin-multiplatform-applications-what-companies-use-kmp-in-pro" id="where-can-i-find-a-list-of-real-life-kotlin-multiplatform-applications-what-companies-use-kmp-in-pro"></a>

이미 Kotlin Multiplatform을 프로덕션에 채택한 다른 회사의 [사례 연구 목록을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/case-studies.html) 확인하세요 .

#### Kotlin Multiplatform과 호환되는 운영체제는 무엇인가요?﻿ <a href="#which-operating-systems-can-work-with-kotlin-multiplatform" id="which-operating-systems-can-work-with-kotlin-multiplatform"></a>

iOS를 제외한 공유 코드 또는 플랫폼별 코드로 작업하려는 경우 IDE에서 지원하는 모든 운영 체제에서 작업할 수 있습니다.

[권장 IDE](https://www.jetbrains.com/help/kotlin-multiplatform-dev/recommended-ides.html) 에 대해 자세히 알아보세요 .

iOS 전용 코드를 작성하고 시뮬레이터나 실제 장치에서 iOS 애플리케이션을 실행하려면 macOS가 설치된 Mac을 사용하세요. 이는 iOS 시뮬레이터가 Apple 요구 사항에 따라 macOS에서만 실행될 수 있지만 Microsoft Windows 또는 Linux와 같은 다른 운영 체제에서는 실행될 수 없기 때문입니다.

#### Kotlin Multiplatform 프로젝트에서 동시 코드를 작성하려면 어떻게 해야 하나요?﻿ <a href="#how-can-i-write-concurrent-code-in-kotlin-multiplatform-projects" id="how-can-i-write-concurrent-code-in-kotlin-multiplatform-projects"></a>

코루틴과 흐름을 사용하여 Kotlin Multiplatform 프로젝트에서 비동기 코드를 작성할 수 있습니다. 이 코드를 호출하는 방법은 코드를 호출하는 위치에 따라 다릅니다. Kotlin 코드에서 정지 함수 및 흐름을 호출하는 방법은 특히 Android에 대해 널리 문서화되어 있습니다. [Swift 코드에서 호출하려면](https://kotlinlang.org/docs/native-ios-integration.html#calling-kotlin-suspending-functions) 약간의 추가 작업이 필요합니다. 자세한 내용은 [KT-47610을 참조하세요.](https://youtrack.jetbrains.com/issue/KT-47610)

Swift에서 일시 중지 함수 및 흐름을 호출하는 가장 좋은 현재 접근 방식은 [KMP-NativeCoroutine](https://github.com/rickclephas/KMP-NativeCoroutines) 또는 [SKIE](https://skie.touchlab.co/)`async` 와 같은 플러그인 및 라이브러리를 Swift의 / `await`또는 Combine 및 RxSwift와 같은 라이브러리 와 함께 사용하는 것입니다. 현재 KMP-NativeCoroutine은 더욱 검증된 솔루션이며 동시성에 대한 `async`/ `await`, Combine 및 RxSwift 접근 방식을 지원합니다. SKIE는 설정하기 쉽고 덜 장황합니다. 예를 들어 Kotlin을 `Flow`Swift에 직접 매핑합니다 `AsyncSequence`. 이 두 라이브러리 모두 코루틴의 적절한 취소를 지원합니다.

사용 방법을 알아보려면 [iOS와 Android 간에 더 많은 로직 공유를](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-upgrade-app.html) 참조하세요 .

#### Kotlin/Native란 무엇이며 Kotlin 멀티플랫폼과 어떤 관련이 있나요?﻿ <a href="#what-is-kotlin-native-and-how-does-it-relate-to-kotlin-multiplatform" id="what-is-kotlin-native-and-how-does-it-relate-to-kotlin-multiplatform"></a>

[Kotlin/Native](https://kotlinlang.org/docs/native-overview.html) 는 Kotlin 코드를 가상 머신 없이 실행할 수 있는 네이티브 바이너리로 컴파일하는 기술입니다. 여기에는 Kotlin 컴파일러용 [LLVM 기반](https://llvm.org/) 백엔드와 Kotlin 표준 라이브러리의 기본 구현이 포함되어 있습니다.

Kotlin/Native는 기본적으로 임베디드 장치 및 iOS와 같이 가상 머신이 바람직하지 않거나 가능하지 않은 플랫폼에 대한 컴파일을 허용하도록 설계되었습니다. 추가 런타임이나 가상 머신이 필요하지 않은 독립형 프로그램을 생성해야 할 때 특히 적합합니다.

예를 들어 모바일 애플리케이션에서 Kotlin으로 작성된 공유 코드는 Kotlin/JVM을 사용하여 Android용 JVM 바이트코드로 컴파일되고 Kotlin/Native를 사용하여 iOS용 네이티브 바이너리로 컴파일됩니다. 두 플랫폼 모두에서 Kotlin Multiplatform과 원활하게 통합됩니다.

<figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/kotlin-native-and-jvm-binaries.png" alt="Kotlin/Native 및 Kotlin/JVM 바이너리" height="352" width="350"><figcaption></figcaption></figure>

#### 네이티브 플랫폼(iOS, macOS, Linux)용 Kotlin 다중 플랫폼 모듈 컴파일 속도를 높이려면 어떻게 해야 하나요?﻿ <a href="#how-can-i-speed-up-my-kotlin-multiplatform-module-compilation-for-native-platforms-ios-macos-linux" id="how-can-i-speed-up-my-kotlin-multiplatform-module-compilation-for-native-platforms-ios-macos-linux"></a>

[Kotlin/Native 컴파일 시간을 개선하려면](https://kotlinlang.org/docs/native-improving-compilation-time.html) 다음 팁을 참조하세요 .

### 멀티플랫폼 작성﻿ <a href="#compose-multiplatform" id="compose-multiplatform"></a>

#### Compose 멀티플랫폼이란 무엇입니까?﻿ <a href="#what-is-compose-multiplatform" id="what-is-compose-multiplatform"></a>

[Compose Multiplatform은](https://www.jetbrains.com/lp/compose-multiplatform/) 소량의 Kotlin 코드로 사용자 인터페이스를 구축하는 간단한 방법을 제공하는 JetBrains에서 개발한 현대적인 선언적 및 반응형 UI 프레임워크입니다. 또한 UI를 한 번 작성하면 iOS, Android, 데스크톱(Windows, macOS, Linux) 및 웹 등 지원되는 플랫폼에서 실행할 수 있습니다.

#### Android용 Jetpack Compose와 어떤 관련이 있나요?﻿ <a href="#how-does-it-relate-to-jetpack-compose-for-android" id="how-does-it-relate-to-jetpack-compose-for-android"></a>

Compose Multiplatform은 대부분의 API를 Google에서 개발한 Android UI 프레임워크인 [Jetpack Compose](https://developer.android.com/jetpack/compose) 와 공유합니다. 실제로 Compose Multiplatform을 사용하여 Android를 타겟팅하는 경우 앱은 Jetpack Compose에서 실행됩니다. Compose Multiplatform을 대상으로 하는 다른 플랫폼에는 내부적으로 Android의 Jetpack Compose와 다른 구현 세부정보가 있을 수 있지만 여전히 동일한 API를 제공합니다.

#### 어떤 플랫폼 간에 UI를 공유할 수 있나요?﻿ <a href="#between-which-platforms-can-i-share-my-ui" id="between-which-platforms-can-i-share-my-ui"></a>

Android, iOS, 데스크톱(Linux, macOS, Windows) 및 웹(Wasm 기반) 등 인기 있는 플랫폼의 모든 조합 간에 UI를 공유할 수 있는 옵션이 있기를 바랍니다. 그러나 Compose Multiplatform은 현재 Android 및 데스크톱에서만 안정적입니다. 자세한 내용은 [지원되는 플랫폼을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/supported-platforms.html) 참조하세요 .

#### 프로덕션에서 Compose Multiplatform을 사용할 수 있나요?﻿ <a href="#can-i-use-compose-multiplatform-in-production" id="can-i-use-compose-multiplatform-in-production"></a>

Compose Multiplatform의 Android 및 데스크톱 대상은 안정적입니다. 프로덕션에서 사용할 수 있습니다.

iOS 타겟은 베타 버전입니다. 이는 기능이 완성되었음을 의미합니다. 프로덕션에서 사용할 수 있으며 마이그레이션 문제가 최소화될 것으로 예상되지만 변경 사항 및 지원 중단 경고에 주의하세요.

WebAssembly를 기반으로 하는 웹용 Compose Multiplatform 버전은 알파 버전입니다. 이는 활발히 개발 중이라는 의미입니다. 주의해서 사용하면 마이그레이션 문제가 발생할 수 있습니다. iOS, Android, 데스크톱용 Compose Multiplatform과 동일한 UI가 있습니다.

#### 새 Compose Multiplatform 프로젝트를 만들려면 어떻게 해야 하나요?﻿ <a href="#how-do-i-create-a-new-compose-multiplatform-project" id="how-do-i-create-a-new-compose-multiplatform-project"></a>

[Compose Multiplatform 시작하기](https://www.jetbrains.com/help/kotlin-multiplatform-dev/compose-multiplatform-getting-started.html) 튜토리얼 에서는 Android, iOS, 데스크톱용 Compose Multiplatform을 사용하여 Kotlin 다중 플랫폼 프로젝트를 만들기 위한 단계별 지침을 제공합니다. Kotlin Developer Advocate Sebastian Aigner가 제작한 YouTube [비디오 튜토리얼을](https://www.youtube.com/watch?v=5\_W5YKPShZ4) 시청할 수도 있습니다 .

#### Compose Multiplatform으로 앱을 빌드하려면 어떤 IDE를 사용해야 하나요?﻿ <a href="#what-ide-should-i-use-for-building-apps-with-compose-multiplatform" id="what-ide-should-i-use-for-building-apps-with-compose-multiplatform"></a>

프로젝트 요구사항과 기대치에 따라 JetBrains Fleet 코드 편집기 또는 Android Studio IDE를 사용하는 것이 좋습니다. 다양한 IDE를 사용하거나 Swift 코드 작성을 위해 Xcode로 전환하지 않고 새로운 멀티플랫폼 경험을 시도하려면 [JetBrains Fleet 튜토리얼을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/fleet.html) 사용해 보세요 .

어떤 것을 선택할지에 대한 자세한 내용은 [권장 IDE 및 코드 편집기를](https://www.jetbrains.com/help/kotlin-multiplatform-dev/recommended-ides.html) 참조하세요 .

#### 데모 애플리케이션으로 플레이할 수 있나요? 어디서 찾을 수 있나요?﻿ <a href="#can-i-play-with-a-demo-application-where-can-i-find-it" id="can-i-play-with-a-demo-application-where-can-i-find-it"></a>

[우리의 샘플을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-samples.html) 가지고 놀 수 있습니다 .

#### Compose Multiplatform에는 위젯이 제공되나요?﻿ <a href="#does-compose-multiplatform-come-with-widgets" id="does-compose-multiplatform-come-with-widgets"></a>

[예, Compose Multiplatform은 Material 3](https://m3.material.io/) 위젯을 완벽하게 지원합니다 .

#### 머티리얼 위젯의 모양을 어느 정도까지 맞춤설정할 수 있나요?﻿ <a href="#to-what-extent-can-i-customize-the-appearance-of-material-widgets" id="to-what-extent-can-i-customize-the-appearance-of-material-widgets"></a>

Material의 테마 기능을 사용하여 색상, 글꼴, 패딩을 맞춤설정할 수 있습니다. 독특한 디자인을 만들고 싶다면 사용자 정의 위젯과 레이아웃을 만들 수 있습니다.

#### 기존 Kotlin Multiplatform 앱에서 UI를 공유할 수 있나요?﻿ <a href="#can-i-share-the-ui-in-my-existing-kotlin-multiplatform-app" id="can-i-share-the-ui-in-my-existing-kotlin-multiplatform-app"></a>

애플리케이션이 UI에 기본 API를 사용하는 경우(가장 일반적인 경우) 상호 운용성을 제공하므로 일부 부분을 Compose Multiplatform에 점진적으로 다시 작성할 수 있습니다. 기본 UI를 Compose로 작성된 일반 UI를 래핑하는 특수 Interop 뷰로 바꿀 수 있습니다.

#### Jetpack Compose를 사용하는 기존 Android 애플리케이션이 있습니다. 다른 플랫폼으로 마이그레이션하려면 어떻게 해야 합니까?﻿ <a href="#i-have-an-existing-android-application-that-uses-jetpack-compose-what-should-i-do-to-migrate-it-to-o" id="i-have-an-existing-android-application-that-uses-jetpack-compose-what-should-i-do-to-migrate-it-to-o"></a>

앱 마이그레이션은 UI 마이그레이션과 로직 마이그레이션의 두 부분으로 구성됩니다. 마이그레이션의 복잡성은 애플리케이션의 복잡성과 사용하는 Android 관련 라이브러리의 양에 따라 달라집니다. 대부분의 화면을 변경 없이 Compose Multiplatform으로 마이그레이션할 수 있습니다. 모든 Jetpack Compose 위젯이 지원됩니다. 그러나 일부 API는 Android 대상에서만 작동합니다. Android 전용이거나 아직 다른 플랫폼으로 포팅되지 않았을 수 있습니다. 예를 들어 리소스 처리는 Android에만 해당되므로 [Compose Multiplatform 리소스 라이브러리](https://www.jetbrains.com/help/kotlin-multiplatform-dev/compose-images-resources.html) 로 마이그레이션하거나 커뮤니티 솔루션을 사용해야 합니다 . Android [탐색 라이브러리](https://developer.android.com/jetpack/androidx/releases/navigation) 도 Android 전용이지만 사용 가능한 [커뮤니티 대안이](https://www.jetbrains.com/help/kotlin-multiplatform-dev/compose-navigation-routing.html) 있습니다 . Android에서만 사용할 수 있는 구성요소에 대한 자세한 내용은 현재 [Android 전용 API 목록을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/compose-android-only-components.html) 참조하세요 .

[비즈니스 로직을 Kotlin Multiplatform으로 마이그레이션](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-integrate-in-existing-app.html) 해야 합니다 . 코드를 공유 모듈로 이동하려고 하면 Android 종속성을 사용하는 부분이 컴파일을 중지하고 다시 작성해야 합니다.

* 대신 Android 전용 종속성을 사용하는 코드를 다시 작성하여 다중 플랫폼 라이브러리를 사용할 수 있습니다. 일부 라이브러리는 이미 Kotlin Multiplatform을 지원하므로 변경할 필요가 없습니다. [KMP-awesome](https://github.com/terrakok/kmp-awesome) 라이브러리 목록을 확인하실 수 있습니다 .
* 또는 플랫폼별 로직에서 공통 코드를 분리하고 플랫폼에 따라 다르게 구현되는 [공통 인터페이스를 제공할](https://www.jetbrains.com/help/kotlin-multiplatform-dev/multiplatform-connect-to-apis.html) 수 있습니다. Android에서는 구현 시 기존 기능을 사용할 수 있으며 iOS와 같은 다른 플랫폼에서는 공통 인터페이스에 대한 새로운 구현을 제공해야 합니다.

#### Compose 화면을 기존 iOS 앱에 통합할 수 있나요?﻿ <a href="#can-i-integrate-compose-screens-into-an-existing-ios-app" id="can-i-integrate-compose-screens-into-an-existing-ios-app"></a>

예. Compose Multiplatform은 다양한 통합 시나리오를 지원합니다. iOS UI 프레임워크와의 통합에 대한 자세한 내용은 [SwiftUI와 통합](https://www.jetbrains.com/help/kotlin-multiplatform-dev/compose-swiftui-integration.html) 및 [UIKit과 통합을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/compose-uikit-integration.html) 참조하세요 .

#### UIKit 또는 SwiftUI 구성 요소를 Compose 화면에 통합할 수 있나요?﻿ <a href="#can-i-integrate-uikit-or-swiftui-components-into-a-compose-screen" id="can-i-integrate-uikit-or-swiftui-components-into-a-compose-screen"></a>

그래 넌 할수있어. [SwiftUI와 통합](https://www.jetbrains.com/help/kotlin-multiplatform-dev/compose-swiftui-integration.html) 및 [UIKit과 통합을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/compose-uikit-integration.html) 참조하세요 .

#### 모바일 OS가 시스템 구성 요소의 시각적 스타일이나 해당 동작을 업데이트하고 변경하면 어떻게 됩니까?﻿ <a href="#what-happens-when-my-mobile-os-updates-and-changes-the-visual-style-of-the-system-components-or-thei" id="what-happens-when-my-mobile-os-updates-and-changes-the-visual-style-of-the-system-components-or-thei"></a>

모든 구성 요소가 캔버스에 그려지기 때문에 OS 업데이트 후에도 UI는 동일하게 유지됩니다. 기본 iOS 구성 요소를 화면에 포함하는 경우 업데이트로 인해 모양이 영향을 받을 수 있습니다.

### 향후 계획﻿ <a href="#future-plans" id="future-plans"></a>

#### Kotlin 멀티플랫폼 발전을 위한 계획은 무엇인가요?﻿ <a href="#what-are-the-plans-for-the-kotlin-multiplatform-evolution" id="what-are-the-plans-for-the-kotlin-multiplatform-evolution"></a>

JetBrains는 멀티플랫폼 개발을 위한 최고의 경험을 제공하고 멀티플랫폼 사용자의 기존 고통을 없애기 위해 많은 투자를 하고 있습니다. 우리는 핵심 Kotlin Multiplatform 기술, Apple 생태계와의 통합, 도구, Compose Multiplatform UI 프레임워크를 개선할 계획을 가지고 있습니다. [우리의 로드맵을 확인해 보세요](https://blog.jetbrains.com/kotlin/2023/11/kotlin-multiplatform-development-roadmap-for-2024/) .

#### Compose Multiplatform은 언제 안정화되나요?﻿ <a href="#when-will-compose-multiplatform-become-stable" id="when-will-compose-multiplatform-become-stable"></a>

Compose Multiplatform은 Android 및 데스크톱에서 안정적이며 iOS 플랫폼 지원은 베타 버전이고 웹은 알파 버전입니다. 우리는 iOS와 웹 플랫폼 모두를 위한 안정적인 출시를 위해 노력하고 있으며 정확한 날짜는 발표될 예정입니다.

안정성 상태에 대한 자세한 내용은 [지원되는 플랫폼을](https://www.jetbrains.com/help/kotlin-multiplatform-dev/supported-platforms.html) 참조하세요 .

#### Kotlin 및 Compose Multiplatform의 웹 대상에 대한 향후 지원은 어떻게 되나요?﻿ <a href="#what-about-future-support-for-web-targets-in-kotlin-and-compose-multiplatform" id="what-about-future-support-for-web-targets-in-kotlin-and-compose-multiplatform"></a>

우리는 현재 큰 잠재력을 보여주는 WebAssembly(Wasm)에 리소스를 집중하고 있습니다. 새로운 [Kotlin/Wasm 백엔드](https://kotlinlang.org/docs/wasm-overview.html) 와 Wasm에서 제공하는 [웹용 Compose Multiplatform을](https://kotl.in/wasm-compose-example) 실험해 볼 수 있습니다 .

JS 대상의 경우 Kotlin/JS 백엔드는 이미 Stable 상태에 도달했습니다. Compose Multiplatform에서는 리소스 제약으로 인해 초점을 JS Canvas에서 Wasm으로 전환했습니다. 이는 더 많은 가능성이 있다고 믿습니다.

또한 이전에 웹용 Compose Multiplatform으로 알려진 Compose HTML도 제공합니다. Kotlin/JS에서 DOM 작업을 위해 설계된 추가 라이브러리이며 플랫폼 간에 UI를 공유하기 위한 것이 아닙니다.

#### 다중 플랫폼 개발을 위한 도구를 개선할 계획이 있습니까?﻿ <a href="#are-there-any-plans-to-improve-tooling-for-multiplatform-development" id="are-there-any-plans-to-improve-tooling-for-multiplatform-development"></a>

예, 우리는 멀티플랫폼 툴링과 관련된 현재의 과제를 잘 인식하고 있으며 여러 영역의 개선을 위해 적극적으로 노력하고 있습니다.

[우리는 이미 Fleet에서 Kotlin 다중 플랫폼 지원](https://www.jetbrains.com/help/kotlin-multiplatform-dev/fleet.html) 미리보기를 출시했습니다 . 직접 사용해보시고 피드백을 남겨주세요!

#### Swift 상호 운용성을 제공할 예정인가요?﻿ <a href="#are-you-going-to-provide-a-swift-interop" id="are-you-going-to-provide-a-swift-interop"></a>

예. 현재 우리는 Kotlin 코드를 Swift로 내보내는 데 중점을 두고 Swift와의 직접적인 상호 운용성을 제공하기 위한 다양한 접근 방식을 조사하고 있습니다.
