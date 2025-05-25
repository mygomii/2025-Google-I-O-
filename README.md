# 2025 Google IO

<summary><strong>Android’s Kotlin Multiplatform announcements at Google I/O and KotlinConf 25 (KMP관련 요약)</strong></summary>

## **Jetpack 라이브러리의 KMP 지원 확대**

Google은 Android와 iOS 간의 비즈니스 로직 공유를 위해 Jetpack 라이브러리에 KMP 지원을 추가하고 있음지난해 `Room`, `DataStore`, `Collection` 라이브러리에 `KMP` 지원을 시작했으며, 현재는 `ViewModel`, `SavedState`, `Paging` 라이브러리에도 지원을 확대하고 있습니다. Jetpack 라이브러리의 플랫폼별 지원 수준은 세 가지 계층으로 분류되며, 최상위 계층은 Android, iOS, JVM을 포함함

| **라이브러리** | **상태** | **설명** |
| --- | --- | --- |
| Room | Stable | DB 사용 가능 (SQLDelight 대안으로 각광) |
| DataStore | Stable | SharedPreferences 대체 가능 |
| Collection | Stable | Kotlin 표준 컬렉션 확장 지원 |
| ViewModel | Alpha | 화면 상태 공유 가능 (Compose에서 활용) |
| SavedState | Alpha | 상태 저장 및 복구 |
| Lifecycle | Alpha | 수명 주기 기반 로직 분리 가능 |
| Paging | Alpha | 페이지 단위 데이터 로딩 지원 |

---

## **도구 개선**

Android Studio에서는 KMP를 앱에 쉽게 통합할 수 있도록 새로운 모듈 템플릿을 제공하고 있음 이를 통해 기존 앱에 새로운 모듈을 추가하고 iOS 및 기타 지원되는 KMP 플랫폼에 코드를 공유할 수 있음

또한, Android Studio는 `Kotlin K2` 모드를 지원하여 Live Edit, Compose Preview 등 언어 지원이 필요한 Android 전용 기능을 사용할 수 있음

- **KMP Shared Module 템플릿**이 Android Studio에 추가됨
    
    → 기존 Android 프로젝트에 iOS용 공유 모듈을 쉽게 붙일 수 있음
    
    → Wizard 형태로 제공되어 입문자도 쉽게 구성 가능
    
- **KSP2 (Kotlin Symbol Processing v2)** 도입
    
    → KMP에서도 annotation processor 사용 가능 (예: Room entity 자동 생성)
    
- **Android Lint for Kotlin**
    
    → 멀티플랫폼 코드에서도 정적 분석이 가능해짐 (버그 사전 탐지)
    

---

## **Google의 KMP 활용 사례**

Google Workspace는 지난해부터 KMP를 실험적으로 도입하였으며, 현재는 iOS용 Google Docs 앱에서 프로덕션 환경에서 실행되고 있음 앱의 런타임 성능은 이전과 동등하거나 더 우수함

이러한 대규모 앱에서 KMP를 테스트함으로써 문제를 식별하고 수정하여 KMP 개발자 커뮤니티에 도움이 되고 있음

예를 들어, Kotlin Native 컴파일러를 LLVM 16으로 업그레이드하고, 더 효율적인 가비지 컬렉터 및 문자열 구현을 기여함 또한, Android Lint의 정적 분석 기능을 Kotlin 대상에 도입하고, AGP와 KGP 모두에 대해 통합된 Gradle DSL을 제공하여 플러그인 관리 경험을 개선하고 있음

- **Google Docs (iOS)**
    
    → 기존 iOS 코드 일부를 제거하고 KMP로 비즈니스 로직을 통합
    
    → 런타임 성능 유지하면서도 코드 재사용 증가
    

---

## **새로운 가이드**

Google은 독립적인 Android 및 iOS 앱에서 공유 비즈니스 로직으로 전환하는 데 도움이 되는 두 가지 새로운 코드랩을 제공

- Kotlin Multiplatform 시작하기
- Room 데이터베이스를 KMP로 마이그레이션하기

---

## **Kotlin 개선 사항**

Kotlin Symbol Processing(KSP2)은 새로운 Kotlin 언어 기능을 더 잘 지원하고 성능을 향상시키기 위해 안정화됨 KSP2는 빌드 시스템과의 통합이 용이하고, 스레드 안전하며, 어노테이션 프로세서 디버깅 지원이 향상되었음 KSP1과 달리, KSP2는 다양한 Kotlin 버전 간의 호환성이 훨씬 뛰어남. 또한, 명령줄 인터페이스가 컴파일러 플러그인이 아닌 독립 실행형 프로그램으로 재작성되어 사용이 크게 간편해짐

https://android-developers.googleblog.com/2025/05/android-kotlin-multiplatform-google-io-kotlinconf-2025.html?utm_source=chatgpt.com
