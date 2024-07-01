# 로드맵

최근 [코틀린 멀티플랫폼이 안정화](https://blog.jetbrains.com/ko/kotlin/2023/11/kotlin-multiplatform-stable/)되면서 이제 전 세계 개발 팀은 안심하고 원활하게 이를 프로덕션에 채택할 수 있게 되었습니다. 하지만 이는 KMP와 에코시스템의 시작일 뿐입니다. 최고의 크로스 플랫폼 개발 경험을 제공하기 위해 JetBrains는 2024년에 핵심 코틀린 멀티플랫폼 기술, 컴포즈 멀티플랫폼, KMP 도구 및 KMP 라이브러리에 대한 다양한 추가 개선 사항을 제공하는 데 목표를 두고 있습니다. 이와 관련하여 JetBrains의 계획과 우선 순위를 알아보려면 계속 읽어보세요.

### 컴포즈 멀티플랫폼 <a href="#compose-multiplatform" id="compose-multiplatform"></a>

지원되는 모든 플랫폼에서 동일하게 보이는, 아름답고 성능이 뛰어난 애플리케이션을 만들 수 있는 프레임워크인 [컴포즈 멀티플랫폼](https://www.jetbrains.com/ko-kr/lp/compose-multiplatform/)을 개발하기 위해 최선을 다하고 있습니다. 현재는 **Compose for iOS를 베타 버전으로** 제공하는 데 중점을 두고 있지만 다른 작업도 진행 중입니다. 앞으로의 계획은 다음과 같습니다.

* 모든 Jetpack Compose의 핵심 API와 구성요소를 멀티플랫폼으로 만듭니다.
* iOS의 렌더링 성능을 향상시킵니다.
* Compose for iOS 앱의 스크롤 및 텍스트 편집이 iOS 기본 앱과 동일하게 작동하도록 만듭니다.
* 모든 유형의 리소스를 공유하기 위한 공통 API를 구현합니다.
* iOS 및 데스크톱 접근성 API와 통합합니다.
* 멀티플랫폼 탐색을 위한 솔루션을 제공합니다.

앞서 언급한 많은 개선 사항은 Compose for Desktop에도 적용 됩니다. 또한, 프로덕션에서 사용하는 분들로부터 받은 피드백을 반영하여 안정성을 개선하고 발전시키키 위해 노력하고 있습니다.

또한 Compose for Web, 특히 Wasm의 가능성을 탐구하는 작업을 계속 진행할 것입니다. 가장 가까운 목표는 알파 단계로 진행시키는 것이며, 여기에는 다음이 포함됩니다.

* 기존 앱을 이식하고 모든 공통 코드를 재사용할 수 있도록 합니다.
* 다양한 화면 크기, 방향 및 해상도를 지원합니다.
* 마우스, 터치스크린, 물리적 키보드 또는 화면 키보드를 통한 입력을 지원합니다.
* 성능 및 바이너리 크기를 개선합니다.

### 툴링(Tooling) <a href="#tooling" id="tooling"></a>

코틀린 멀티플랫폼을 위한 훌륭한 IDE 환경을 제공하기 위해 최선을 다하고 있습니다. 이는 핵심 플랫폼에 투자하고, 예를 들어 코틀린 IDE 플러그인을 K2 컴파일러 프런트엔드로 마이그레이션하는 것뿐만 아니라 통합하는 모든 코틀린 멀티플랫폼 타깃과 코드 베이스에 대한 단일 도구([Fleet](https://www.jetbrains.com/ko-kr/fleet/))를 제공하여 여러 IDE 사이에서 지속적으로 전환할 필요가 없도록 한다는 것을 의미합니다.

[Kotlin Multiplatform 개발을 위한 Fleet 사용](https://www.jetbrains.com/help/kotlin-multiplatform-dev/fleet.html)에 대한 귀하의 피드백을 신속하고 반복적으로 수렴하여 개발 경험을 향상시키는 데 필요한 모든 환경이 갖춰지도록 할 계획입니다. 특히 다음 영역이 해당됩니다.

* 공통 코드에 대한 실시간 미리보기 및 시각적 디버그 도구를 포함하여 컴포즈 멀티플랫폼에 대한 지원 개선
* 프로젝트 구성을 도와주는 IDE
* 멀티플랫폼 프로젝트의 모든 부분에 대한 통합되고 향상된 디버깅 경험

### 멀티플랫폼의 핵심 <a href="#multiplatform-core" id="multiplatform-core"></a>

코틀린 멀티플랫폼을 사용하는 주요 시나리오 중 하나는 iOS 타깃과 코드를 공유하는 것입니다. 코드 베이스에서 코틀린 멀티플랫폼 프레임워크를 사용하여 작업하는 iOS 개발자의 개발 경험을 개선하는 데 중점을 두려고 합니다.

이 영역에서 주요 이니셔티브는 **Kotlin에서 Swift로 직접 내보내기**입니다. Objective-C 병목 현상을 제거하여 더 광범위한 Swift 언어 지원과 더 자연스러운 API 내보내기가 가능해집니다. 또한 코틀린 라이브러리 작성자를 특히 염두에 두고 도구를 만들고 있습니다. 이러한 도구는 Swift로 내보낼 때 Kotlin API의 호환성과 사용자 친화성을 개선하도록 설계되었습니다. 도구 개발에도 세심한 주의를 기울이고 있습니다. IDE와 빌드 시스템은 개발자 경험의 필수적인 부분이며, Swift Export가 원활하게 통합되도록 하는 것이 목표입니다.

다른 이니셔티브에는 Kotlin/Native 컴파일링 속도 향상, CocoaPods 통합 강화, SwiftPM을 사용한 프레임워크 내보내기 지원 도입 등이 포함됩니다.

또한 코틀린 멀티플랫폼 애플리케이션의 빌드 설정을 개선하기 위한 방법을 계속해서 탐구할 계획입니다. Kotlin 1.9.20에서는 Gradle Multiplatform DSL을 [대폭적으로 개선](https://kotlinlang.org/docs/whatsnew1920.html#kotlin-multiplatform)하여 읽고 쓰기가 더 쉽도록 했습니다. 계속해서 점진적으로 개선해 나갈 예정입니다. 또한 사용 편의성, 온보딩 및 IDE 지원에 초점을 맞춘 새로운 프로젝트 구성 도구인 [Amper](https://blog.jetbrains.com/ko/blog/2023/11/27/amper-improving-the-build-tooling-user-experience/)가 실험적 단계에 있습니다.

### 라이브러리 에코시스템 <a href="#library-ecosystem" id="library-ecosystem"></a>

코틀린 멀티플랫폼 에코시스템이 빠르게 성장함에 따라 라이브러리의 이전 버전과의 호환성이 중요해졌습니다. 이를 보장하려면 JetBrains 팀과 라이브러리 작성자가 서로 협력해야 합니다. 계획은 다음과 같습니다.

* 라이브러리 작성자가 JVM 라이브러리 빌드 지식을 활용할 수 있도록 klib 형식을 개선합니다.
* JVM과 마찬가지로 코틀린 멀티플랫폼 라이브러리에서 동일한 코드 인라인 동작을 구현합니다.
* 멀티플랫폼 라이브러리 공개 API가 호환되지 않는 방식으로 변경되지 않았는지 확인하는 도구를 제공합니다.

KMP 라이브러리의 게시 프로세스도 개선할 예정입니다. 구체적으로 다음을 계획하고 있습니다.

* Mac 컴퓨터 없이도 KMP 라이브러리를 빌드하고 게시할 수 있도록 합니다.
* KMP 라이브러리를 생성하고 게시하기 위한 템플릿과 광범위한 가이드라인을 제공합니다.

코틀린 멀티플랫폼이 이제 안정화되었지만 아직 중요한 업데이트가 계획되어 있습니다. 하지만 현재 형식으로 빌드된 라이브러리가 최신 코틀린 버전에서도 계속 작동할 것이므로 걱정하지 마세요.

### 더 읽어보기 <a href="#undefined" id="undefined"></a>

* [Kotlin Multiplatform이 안정화되어 프로덕션에 사용할 수 있습니다](https://blog.jetbrains.com/ko/kotlin/2023/11/kotlin-multiplatform-stable/)
* [Compose Multiplatform 1.5.10 – 시작한다면 지금입니다](https://blog.jetbrains.com/ko/kotlin/2023/11/compose-multiplatform-1-5-10-release/)
* [Amper – 빌드 도구 사용자 경험 개선](https://blog.jetbrains.com/ko/blog/2023/11/27/amper-improving-the-build-tooling-user-experience/)
* [Kotlin Multiplatform 도구가 포함된 Fleet을 만나보세요](https://blog.jetbrains.com/ko/kotlin/2023/11/kotlin-multiplatform-tooling-in-fleet/)
* [Kotlin 로드맵](https://kotlinlang.org/docs/roadmap.html#roadmap-details)

