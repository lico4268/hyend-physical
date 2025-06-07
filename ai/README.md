# AI Integration Module

이 디렉토리는 로봇의 지능적 대화와 감정 분석을 담당하는 핵심 AI 모듈입니다.  
음성 → 텍스트(STT) → 감정 인식 + 응답 생성(LLM) → 음성 출력(TTS)의 파이프라인으로 구성됩니다.

---

## 🧠 주요 처리 흐름
1. **STT (Speech-to-Text)**: 사용자 음성을 Whisper AI 등으로 텍스트화 -> 일단은 로봇에서 진행할 예정
2. **LLM 호출**: 구조화된 프롬프트로 응답 + 감정 추출 (GPT / Gemini)
3. **감정 분석**: 텍스트에서 감정 범주 분류 (`happy`, `sad`, `angry`, ...)
4. **TTS (Text-to-Speech)**: gTTS or soVITS로 음성 출력
5. **맥락 기반 감정 이력 추적**: 대화의 흐름에 따른 감정 변화 관리

---

## 💬 프롬프트 예시
```txt
"사용자 메시지에 대한 응답과 함께 감정을 다음 중 하나로 분류하시오: happy, sad, angry, calm, excited"
