# UI 업데이트

사용자 인터페이스를 빌드하려면 프로젝트의 Android 부분에는 [Compose Multiplatform](https://www.jetbrains.com/lp/compose-multiplatform/) 도구 키트를 사용 하고 iOS 부분에는 [SwiftUI를](https://developer.apple.com/xcode/swiftui/) 사용합니다. 둘 다 선언적 UI 프레임워크이며 UI 구현에서 유사점을 볼 수 있습니다. 두 경우 모두 데이터를 변수에 저장 `phrases`하고 나중에 이를 반복하여 항목 목록을 생성합니다 `Text`.

### 안드로이드 부분 업데이트﻿ <a href="#update-the-android-part" id="update-the-android-part"></a>

모듈 `composeApp`은 Android 애플리케이션을 포함하고, 주요 활동과 UI 보기를 정의하며, 모듈을 `shared`일반 Android 라이브러리로 사용합니다. 애플리케이션의 UI는 Compose Multiplatform 프레임워크를 사용합니다.

몇 가지 사항을 변경하고 UI에 어떻게 반영되는지 확인하세요.

1. `App.kt`의 파일 로 이동합니다 `composeApp/src/androidMain/kotlin`.
2. 클래스 호출을 찾으십시오 `Greeting`. 함수를 선택하고 `greet()`마우스 오른쪽 버튼을 클릭한 후 이동 | 선언 또는 사용 메뉴 항목. `shared`이전 단계에서 편집한 모듈 과 동일한 클래스라는 것을 알 수 있습니다 .
3.  에서 함수를 `Greeting.kt`업데이트합니다 `greet()`.

    ```
    fun greet(): List<String> = buildList {
        add(if (Random.nextBoolean()) "Hi!" else "Hello!")
        add("Guess what this is! > ${platform.name.reversed()}!")
    }
    ```

    이제 문자열 목록을 반환합니다.
4.  돌아가서 `App.kt`정의를 업데이트하세요.

    ```
    @Composable
    @Preview
    fun App() {
        MaterialTheme {
            val greeting = remember { Greeting().greet() }

            Column(
                modifier = Modifier.padding(all = 20.dp),
                verticalArrangement = Arrangement.spacedBy(8.dp),
            ) {
                greeting.forEach { greeting ->
                    Text(greeting)
                    Divider()
                }
            }
        }
    }
    ```

    여기서 `Column`컴포저블은 각 `Text`항목을 표시하고 항목 주위에 패딩을 추가하고 항목 사이에 공간을 추가합니다.
5. 누락된 종속성을 가져오려면 Android Studio의 제안을 따르세요.
6.  이제 Android 앱을 실행하여 목록이 어떻게 표시되는지 확인할 수 있습니다.

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/first-multiplatform-project-on-android-2.png" alt="Android 다중 플랫폼 앱의 업데이트된 UI" height="627" width="300"><figcaption></figcaption></figure>

### Xcode에서 iOS 모듈 작업﻿ <a href="#work-with-the-ios-module-in-xcode" id="work-with-the-ios-module-in-xcode"></a>

`iosApp`iOS 애플리케이션에 빌드되는 Xcode 프로젝트입니다. `shared`모듈을 iOS 프레임워크로 사용하고 의존합니다 . 앱의 UI는 Swift로 작성되었습니다.

Android 앱과 동일한 변경 사항을 구현합니다.

1. 프로젝트`iosApp` 도구 창 에서 프로젝트 루트에 있는 폴더를 찾으세요 .
2. 내부에서 폴더를 `iosApp`마우스 오른쪽 버튼으로 클릭 `iosApp.xcodeproj`하고 열기 | 엑스코드 .
3.  파일 에서 함수를 `ContentView.swift`선택 `greet()`하고 바로가기를 사용 ⌃ ⌘ J하거나, 함수 이름을 마우스 오른쪽 버튼으로 클릭하고 정의로 이동 을 선택합니다 .

    모듈에 정의된 Kotlin 함수에 대한 Objective-C 선언을 볼 수 있습니다 `shared`. Kotlin 유형은 Objective-C/Swift에서 사용될 때 Objective-C 유형으로 표시됩니다. 여기서 `greet()`함수는 Kotlin에서 반환 `List<String>`하고 Swift에서는 를 반환하는 것으로 표시됩니다 `NSArray<NSString>`. 유형 매핑에 대한 자세한 내용은 [Swift/Objective-C와의 상호 운용성을](https://kotlinlang.org/docs/native-objc-interop.html) 참조하세요 .
4.  앱을 실행하면 문자열 배열이 표시됩니다. `greet()`함수를 사용하는 Swift 코드는 변경된 선언을 고려하지 않습니다. 항목 목록을 표시하려면 SwiftUI 코드를 업데이트하세요.

    ```
    struct ContentView: View {
        let phrases = Greeting().greet()

        var body: some View {
            List(phrases, id: \.self) {
                Text($0)
            }
        }
    }
    ```

    * 호출 결과는 변수 `greet()`에 저장됩니다 `phrases`( `let`Swift의 경우 Kotlin의 와 유사합니다 `val`).
    * 이 `List`함수는 항목 목록을 생성합니다 `Text`.
5.  앱을 실행하여 변경 사항을 확인하세요.

    <figure><img src="https://resources.jetbrains.com/help/img/kotlin-multiplatform-dev/stable/first-multiplatform-project-on-ios-2.png" alt="iOS 다중 플랫폼 앱의 업데이트된 UI" height="593" width="300"><figcaption></figcaption></figure>

\
