<h1 align="center">정승준 · Seung Joon Jeong</h1>
<p align="center"><strong>Robotics · Computer Vision · AI Agents</strong></p>
<p align="center">인식 결과를 로봇의 동작으로, 학습한 모델을 실제 실행 환경으로 연결합니다.</p>
<p align="center">
  <a href="mailto:vasebull@gmail.com">Email</a> ·
  <a href="https://github.com/tokengeoji/kakaotech-learning-log">Learning Log</a> ·
  <a href="#selected-projects">Selected Projects</a>
</p>

RGB-D 인식과 ROS 2 로봇 제어, 딥러닝 기반 소음제어, LangGraph 기반 에이전트를 개발합니다.<br>
**강원대학교 전자공학과 · 2027년 2월 졸업 예정**<br>
관심 분야: VLA(시각·언어·행동 모델), 멀티모달 모델, AI 에이전트

---

## Selected Projects

| 분야 | 프로젝트 | 직접 다룬 핵심 과제 |
| --- | --- | --- |
| Robotics & Vision | [RGB-D 로봇 인식·접근 제어](https://github.com/tokengeoji/object_detection) | 물체 탐지 → 3D 위치 추정 → 로봇 정렬·접근·정지 |
| Deep Learning | [DeepANC](https://github.com/tokengeoji/Deep-ANC) | 인과적 소음제어 모델과 스트리밍 추론, Jetson 실행 검증 |
| AI Agents | [RE:BORN](https://github.com/kakaotechcampus-4/ktc4-kangwon-4/tree/develop) | 사용자 상황 분석 → 다음 행동 판단 → 결과 검수 |

### 01 · RGB-D 기반 로봇 인식·접근 제어

**학부연구 프로젝트 · 인식 파이프라인 구현 및 로봇 제어 연동**

카메라에서 찾은 물체의 위치를 로봇이 사용할 수 있는 좌표로 바꾸고, 이동로봇의 접근 동작과 연결했습니다.

- 데이터 수집·라벨링과 YOLO 학습을 진행하고, RGB-D 깊이 정보로 물체의 3D 위치를 추정했습니다.
- ROS 2 TF로 카메라 좌표를 로봇 기준 좌표로 변환하고, 위치 조회와 접근 제어를 연동했습니다.
- 목표물을 놓치거나 탐지 정보가 오래되면 정지하도록 처리하고, 갱신된 위치에 맞춰 다시 정렬하도록 구성했습니다.

`Python` `ROS 2` `YOLO` `OpenCV` `RGB-D` `TF`

[인식 코드와 구조](https://github.com/tokengeoji/object_detection) · [접근 제어 코드](https://github.com/tokengeoji/Approach)

### 02 · DeepANC — 딥러닝 기반 능동소음제어

**캡스톤디자인 · 모델 설계·학습 및 추론 구현**

덕트 내 소음을 줄이기 위한 딥러닝 모델을 개발하고, 연속 오디오 입력을 처리하는 추론 경로를 구현했습니다.

- PyTorch 모델의 학습과 스트리밍 추론을 구현하고, 처리 블록 사이에서 모델 상태를 유지하도록 구성했습니다.
- ONNX Runtime 실행 경로를 구성하고, Jetson AGX Orin에서 추론 지연과 실행 환경을 검증했습니다.
- 모델 실행 검증과 실제 음향 감쇠 평가를 구분해 실험 과정과 현재 상태를 기록했습니다.

`Python` `PyTorch` `ONNX Runtime` `Jetson AGX Orin` `Audio Processing`

[코드와 실험 자료](https://github.com/tokengeoji/Deep-ANC) · [모델 구조](https://github.com/tokengeoji/Deep-ANC/blob/main/docs/04_model_architecture.md)

### 03 · RE:BORN — 폐업 절차 안내 AI 에이전트

**카카오테크캠퍼스 팀 프로젝트 · AI 에이전트 개발 · 진행 중**

폐업을 준비하는 소상공인의 상황과 공식 절차 자료를 바탕으로, 다음에 해야 할 일을 안내하는 서비스를 팀으로 개발하고 있습니다.

- LangGraph로 절차 조회, 정보 분석, 행동 판단을 연결하고, 판단 결과를 별도로 검수하는 흐름을 개발했습니다.
- 새 입력이 기존 사실과 충돌하거나 판단 근거가 부족한 경우를 구분하고, 검수를 통과한 판단 결과만 반환하도록 구현했습니다.
- 백엔드 팀과 주고받을 데이터와 저장할 내용을 맞추고, 검수된 절차 자료와 단계별 순서를 다음 행동 판단에 연결했습니다.

`Python` `LangGraph` `Pydantic` `LLM` `Backend Integration`

[팀 저장소](https://github.com/kakaotechcampus-4/ktc4-kangwon-4/tree/develop) · [에이전트 구조](https://github.com/kakaotechcampus-4/ktc4-kangwon-4/blob/develop/docs/agent/architecture.md) · [구현·검증 PR #69](https://github.com/kakaotechcampus-4/ktc4-kangwon-4/pull/69)

---

## Tech Stack

| 영역 | 사용 기술 | 적용 경험 |
| --- | --- | --- |
| Robotics & Vision | Python, ROS 2, OpenCV, YOLO, TF | RGB-D 물체 인식, 좌표 변환, 로봇 접근 제어 |
| Deep Learning | PyTorch, ONNX Runtime, Jetson AGX Orin | 모델 설계·학습, 스트리밍 추론, 계산 지연 검증 |
| AI Agents | LangGraph, LangChain, Pydantic | 실행 흐름 구성, 입력·근거 검증, 백엔드 연동 |
| Embedded & Real-Time | C, TI C2000, OMAP-L138, TI SYS/BIOS, EDMA | 주변장치 제어와 인터럽트, DSP 오디오 처리 실습 |
| Development | Linux, Docker, Git | 개발 환경 구성과 팀 협업 |

## More Work

- **[Action_Decision](https://github.com/tokengeoji/Action_Decision)** — 대화·세션 로그 기반 다음 행동 예측, 모델 조합과 가중치 압축 실험
- **[EmbeddedSystem](https://github.com/tokengeoji/EmbeddedSystem)** — TI C2000 기반 GPIO·인터럽트·타이머·ADC·PWM 제어 실습
- **[RealTimeSystem](https://github.com/tokengeoji/RealTimeSystem)** — TI SYS/BIOS와 EDMA 기반 DSP 오디오 처리 실습
- **[Learning Log](https://github.com/tokengeoji/kakaotech-learning-log)** — 카카오테크캠퍼스 학습 기록

## Background & Awards

- **강원대학교 전자공학과** — 2027년 2월 졸업 예정
- **로봇 SW 연구실 학부연구생** — RGB-D 인식, 3D 위치 추정, ROS 2 제어 연동
- **카카오테크캠퍼스 4기 Agentic AI 과정** — RE:BORN 에이전트 개발
- **캡스톤디자인 페스티벌 금상** — DeepANC 팀 프로젝트
- **카카오테크캠퍼스 아이디어톤 우수상** — 팀 수상

## Contact

프로젝트와 협업에 관한 이야기는 **[vasebull@gmail.com](mailto:vasebull@gmail.com)** 으로 연락해 주세요.
