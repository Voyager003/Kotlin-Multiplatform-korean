# 지원되는 플랫폼

## 지원되는 플랫폼의 안정성 <a href="#supported-platforms.md" id="supported-platforms.md"></a>

코틀린 멀티플랫폼을 사용하면 다양한 플랫폼용 애플리케이션을 만들고 플랫폼 간에 코드를 공유하여 사용자가 원하는 기기에서 접근할 수 있습니다. 각 플랫폼은 코드 공유를 위한 핵심 코틀린 멀티플랫폼 기술과 컴포즈 멀티플랫폼 UI 프레임워크의 지원 수준에 따라 안정성에 차이가 있을 수 있습니다.

이 페이지에는 안정성 수준에 대한 세부 정보와 함께 프로젝트 요구 사항에 맞는 플랫폼을 식별하는 데 도움이 되는 정보가 포함되어 있습니다.

## 핵심 코틀린 멀티플랫폼 기술 안정성 수준﻿

핵심 코틀린 멀티플랫폼 기술의 플랫폼 안정성 수준과 그 의미에 대한 가이드는 다음과 같습니다.

**Experimental**이란 "시험용으로만 사용"을 의미합니다.

* 우리는 단지 아이디어를 시도해 보고 몇몇 사용자들이 그것을 사용해 보고 피드백을 주기를 원합니다. 만약 잘 되지 않으면 언제든지 중단할 수 있습니다.

**Best effort**은 "대부분의 시나리오에서 사용해도 안전하다"는 의미입니다.

* 예상치 못한 주요 변경 사항이 있을 수 있습니다.
* 마이그레이션 중에 문제가 발생할 수 있습니다.

**Stable**은 "가장 보수적인 시나리오에서도 사용할 수 있음"을 의미합니다.

* 작업이 완료된 상태로, 엄격한 [이전 버전과의 호환성 규칙](https://kotlinfoundation.org/language-committee-guidelines/) 에 따라 이를 개발할 것입니다 .

#### 핵심 코틀린 멀티플랫폼 기술의 현재 플랫폼 안정성 수준﻿ <a href="#current-platform-stability-levels-for-the-core-kotlin-multiplatform-technology" id="current-platform-stability-levels-for-the-core-kotlin-multiplatform-technology"></a>

| 플랫폼              | 안정성 수준      |
| ---------------- | ----------- |
| Android          | Stable      |
| iOS              | Stable      |
| 데스크탑(JVM)        | Stable      |
| 서버사이드(JVM)       | Stable      |
| Kotlin/Wasm 기반 웹 | Alpha       |
| Kotlin/JS 기반 웹   | Stable      |
| watchOS          | Best effort |
| tvOS             | Best effort |

코틀린 멀티플랫폼은 여기에 나열된 것보다 더 많은 기본 플랫폼을 지원합니다. 각각에 대한 지원 수준을 이해하려면 [Kotlin/Native 대상 지원을](https://kotlinlang.org/docs/native-target-support.html) 참조하세요 .

코틀린 멀티플랫폼과 같은 Kotlin 구성요소의 안정성 수준에 대한 자세한 내용은 [Kotlin 구성요소의 안정성 수준을](https://kotlinlang.org/docs/components-stability.html#current-stability-of-kotlin-components) 참조하세요 .

### 컴포즈 멀티플랫폼 UI 프레임워크 안정성 수준﻿ <a href="#compose-multiplatform-ui-framework-stability-levels" id="compose-multiplatform-ui-framework-stability-levels"></a>

다음은 컴포즈 멀티플랫폼 UI 프레임워크의 플랫폼 안정성 수준과 그 의미에 대한 빠른 가이드입니다.

**Experimental**이란 "개발 중"을 의미합니다.

* 일부 기능은 아직 제공되지 않을 수 있으며, 현재 제공하는 기능에는 성능 문제나 버그가 있을 수 있습니다.
* 향후 변경이 있을 수 있으며, 주요 변경이 자주 발생할 수 있습니다.

**Alpha**는 “사용자가 위험을 감수하고 사용, 마이그레이션 문제 예상”을 의미합니다:

* 우리는 플랫폼 지원을 제품화하기로 결정했지만 아직 최종 형태를 갖추지 않았습니다.

**Beta**는 “사용할 수 있으며, 마이그레이션 문제를 최소화하기 위해 최선을 다할 것”을 의미합니다:

* 거의 완료되었으므로 이제 사용자 피드백이 특히 중요합니다.
* 아직 100% 완성된 것은 아니므로 변경이 가능합니다. (사용자의 피드백을 바탕으로 한 변경도 포함)

**Experimental** , **Alpha**, **Beta를** 총칭하여 사전 안정 수준 이라고 합니다 .

**Stable**이란 "가장 보수적인 시나리오에서도 사용할 수 있음"을 의미합니다.

* 프레임워크는 자체 성능이나 기타 문제가 발생하지 않고도 프로덕션에 즉시 사용할 수 있는 애플리케이션을 작성할 수 있는 포괄적인 API를 제공합니다.
* API에 대한 주요 변경 사항은 공식 지원 중단 발표 이후 2개 버전에만 적용됩니다.

#### 컴포즈 멀티플랫폼 UI 프레임워크의 현재 플랫폼 안정성 수준 <a href="#current-platform-stability-levels-for-compose-multiplatform-ui-framework" id="current-platform-stability-levels-for-compose-multiplatform-ui-framework"></a>

| 플랫폼              | 안정성 수준 |
| ---------------- | ------ |
| Android          | Stable |
| iOS              | Beta   |
| 데스크탑(JVM)        | Stable |
| Kotlin/Wasm 기반 웹 | Alpha  |

### 다음에 할 일은?﻿ <a href="#what-s-next" id="what-s-next"></a>

다양한 플랫폼 조합에서 코드 공유 시나리오에 어떤 IDE가 더 나은지 알아보려면 [권장 IDE를](https://www.jetbrains.com/help/kotlin-multiplatform-dev/recommended-ides.html) 참조하세요.

\
\
