# 로드맵

최근 [Kotlin Multiplatform의 안정성이](https://blog.jetbrains.com/kotlin/2023/11/kotlin-multiplatform-stable/) 확보됨에 따라 전 세계 개발팀은 이제 원활하고 자신있게 이를 프로덕션에 채택할 수 있습니다. 그러나 이는 KMP와 생태계의 시작일 뿐입니다. 최고의 크로스 플랫폼 개발 경험을 제공하기 위해 JetBrains는 2024년에 핵심 Kotlin 다중 플랫폼 기술, Compose Multiplatform, KMP 도구 및 KMP 라이브러리에 대한 다양한 추가 개선 사항을 제공하는 것을 목표로 하고 있습니다. 계속 읽어서 우리가 계획하고 있는 내용과 내용을 알아보세요. 이 분야에서 우리의 우선순위.

### 멀티플랫폼 작성 <a href="#compose-multiplatform" id="compose-multiplatform"></a>

우리는 [Compose Multiplatform을](https://www.jetbrains.com/lp/compose-multiplatform/) 지원되는 모든 플랫폼에서 동일하게 보이는 아름답고 성능이 뛰어난 애플리케이션을 만들 수 있는 프레임워크로 만들기 위해 최선을 다하고 있습니다. 현재 우리의 주요 초점은 **iOS용 Compose를 베타로** 전환하는 것이지만 다른 작업도 진행 중입니다. 우리가 할 계획은 다음과 같습니다.

* 모든 Jetpack Compose 핵심 API 및 구성요소를 다중 플랫폼으로 만듭니다.
* iOS의 렌더링 성능을 향상시킵니다.
* iOS용 Compose 앱의 스크롤 및 텍스트 편집이 iOS 기본 앱과 동일하게 작동하도록 합니다.
* 모든 유형의 리소스를 공유하기 위한 공통 API를 구현합니다.
* iOS 및 데스크톱 접근성 API와 통합됩니다.
* 다중 플랫폼 탐색을 위한 솔루션을 제공합니다.

앞서 언급한 개선 사항 중 상당수는 Compose for Desktop에도 도움이 됩니다. 또한, 프로덕션에서 사용하시는 분들의 피드백을 반영하여 안정성을 향상시키고 진화시키기 위해 노력하고 있습니다.

또한 Compose for Web, 특히 Wasm을 통해 무엇이 가능한지 계속해서 알아볼 예정입니다. 가장 가까운 목표는 다음을 포함하여 이를 알파로 승격시키는 것입니다.

* 기존 앱을 포팅하고 모든 공통 코드를 재사용할 수 있습니다.
* 다양한 화면 크기, 방향 및 밀도를 지원합니다.
* 마우스, 터치스크린, 물리적 키보드 또는 화면 키보드를 통한 입력을 지원합니다.
* 성능 및 바이너리 크기가 향상되었습니다.

### 압형 <a href="#tooling" id="tooling"></a>

우리는 Kotlin Multiplatform을 위한 훌륭한 IDE 환경을 제공하기 위해 최선을 다하고 있습니다. 이는 핵심 플랫폼에 투자할 뿐만 아니라 Kotlin IDE 플러그인을 K2 컴파일러 프런트엔드로 마이그레이션하는 것뿐만 아니라 이를 통합하는 모든 Kotlin Multiplatform 대상 및 코드베이스에 대해 단일 도구( [Fleet](https://www.jetbrains.com/fleet/) )를 제공하여 지속적으로 전환할 필요가 없음을 의미합니다. 서로 다른 IDE 사이.

[우리는 Kotlin 다중 플랫폼 개발을 위한 Fleet 사용](https://www.jetbrains.com/help/kotlin-multiplatform-dev/fleet.html) 에 대한 피드백을 신속하게 반복하여   훌륭한 개발 경험을 위해 필요한 모든 것을 갖추도록 할 계획입니다. 무엇보다도 우리는 다음 영역을 제공할 예정입니다.

* 일반 코드에 대한 실시간 미리보기 및 시각적 디버깅 도구를 포함하여 Compose Multiplatform에 대한 지원이 향상되었습니다.
* 프로젝트 구성을 도와주는 IDE입니다.
* 멀티플랫폼 프로젝트의 모든 부분에 대한 통합되고 향상된 디버깅 환경입니다.

### 멀티플랫폼 코어 <a href="#multiplatform-core" id="multiplatform-core"></a>

인기 있는 Kotlin 다중 플랫폼 시나리오 중 하나는 iOS 대상과 코드를 공유하는 것입니다. 우리는 코드베이스에서 Kotlin Multiplatform 프레임워크를 사용하여 작업하는 iOS 개발자의 개발 경험에 중점을 두고 싶습니다.

이 분야의 주요 이니셔티브는 **Kotlin에서 Swift로 직접 내보내기** 입니다 . Objective-C 병목 현상을 제거하여 더 광범위한 Swift 언어 지원과 더 자연스러운 API 내보내기가 가능해집니다. 또한 우리는 Kotlin 라이브러리 작성자를 위해 특별히 도구를 만들고 있습니다. 이러한 도구는 Swift로 내보낼 때 Kotlin API의 호환성과 사용자 친화성을 개선하도록 설계되었습니다. 우리는 툴링에도 세심한 주의를 기울이고 있습니다. IDE와 빌드 시스템은 개발자 경험의 필수적인 부분이며, 우리의 목표는 Swift 내보내기가 원활하게 통합되도록 하는 것입니다.

우리의 다른 이니셔티브에는 Kotlin/Native 컴파일 속도 향상, CocoaPods 통합 강화, SwiftPM을 사용한 프레임워크 내보내기 지원 도입이 포함됩니다.

또한 Kotlin 다중 플랫폼 애플리케이션의 빌드 설정을 개선하는 방법을 계속해서 탐색할 계획입니다. Kotlin 1.9.20에서는 Gradle Multiplatform DSL이 [크게 개선](https://kotlinlang.org/docs/whatsnew1920.html#kotlin-multiplatform) 되어 읽고 쓰기가 더 쉬워졌습니다. 계속해서 점진적으로 개선해 나가겠습니다. 또한 유용성, 온보딩 및 IDE 지원에 초점을 맞춘 새로운 프로젝트 구성 도구인 [Amper를 실험하고 있습니다.](https://blog.jetbrains.com/blog/2023/11/09/amper-improving-the-build-tooling-user-experience/)

### 도서관 생태계 <a href="#library-ecosystem" id="library-ecosystem"></a>

Kotlin Multiplatform 생태계가 빠르게 성장함에 따라 라이브러리의 이전 버전과의 호환성이 중요해졌습니다. 이를 보장하려면 JetBrains 팀과 라이브러리 제작자가 협력해야 합니다. 우리의 계획은 다음과 같습니다.

* 라이브러리 작성자가 JVM 라이브러리 구축에 대한 지식을 활용할 수 있도록 klib 형식을 개선합니다.
* JVM과 마찬가지로 Kotlin Multiplatform 라이브러리에서 동일한 코드 인라인 동작을 구현합니다.
* 멀티플랫폼 라이브러리 공개 API가 호환되지 않는 방식으로 변경되지 않았는지 확인하는 도구를 제공하세요.

또한 KMP 라이브러리의 게시 프로세스도 개선할 예정입니다. 특히 KMP 라이브러리 생성 및 게시를 위한 템플릿과 광범위한 지침을 제공할 계획입니다.

Kotlin Multiplatform은 이제 안정적이지만 중요한 업데이트를 계획하고 있습니다. 하지만 걱정하지 마세요. 현재 형식으로 빌드된 라이브러리는 최신 Kotlin 버전에서도 계속 작동합니다.\


### 더 읽어보세요 <a href="#read-more" id="read-more"></a>

* [Kotlin 멀티플랫폼은 안정적이고 생산 준비가 되어 있습니다.](https://blog.jetbrains.com/kotlin/2023/11/kotlin-multiplatform-stable/)
* [Compose Multiplatform 1.5.10 – 시작하기에 완벽한 시기](https://blog.jetbrains.com/kotlin/2023/11/compose-multiplatform-1-5-10-release/)
* [Amper – 빌드 도구 사용자 경험 개선](https://blog.jetbrains.com/blog/2023/11/09/amper-improving-the-build-tooling-user-experience/)
* [Kotlin 다중 플랫폼 도구를 사용한 Welcome Fleet](https://blog.jetbrains.com/kotlin/2023/11/kotlin-multiplatform-tooling-in-fleet/)
* [Kotlin 로드맵](https://kotlinlang.org/docs/roadmap.html#roadmap-details)
