# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 한승엽
- 리뷰어 : 장주휘


# PRT(Peer Review Template)
- [ ]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 최종 결과물로 Epoch 20까지의 학습 로그와 실제 문장 테스트 결과가 첨부되어 있습니다.
    - 평균 Loss가 0.3839까지 하락한 것을 볼 수 있습니다.
      <img width="830" height="1012" alt="image" src="https://github.com/user-attachments/assets/9c780064-d945-4e9a-ad16-91bcafd0bbc9" />


    
- [ ]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - ChatbotDataset 부분이 가장 핵심적이라고 판단됨. 여기서 잘못되면 학습 자체가 불가능하기 때문
    - 구분선과 타이틀 주석 명시 확인 가
    - 각 변수의 역할과 텐서의 형태와 왜 이 작업을 수행해야 하는지가 주석으로 기술하심
    - 주석을 보고 코드 이해가 잘 
        - <img width="1212" height="1026" alt="image" src="https://github.com/user-attachments/assets/3a809d85-017b-4f63-8b60-8b69428798e1" />

        
- [ ]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 초기에 Loss가 발산하던 문제를 배치 사이즈 부족과 너무 높은 학습률 때문임을 알고, 이를 해결하는 과정을 코드 내에 기록
    - 모델의 구조적 변수(num_heads를 8에서 4로 하향 조정)와 SentencePiece 단어장 크기(vocab_size를 5000으로 고정)를 최적화하는 추가적인 실험적 시도하심
        - <img width="1952" height="210" alt="image" src="https://github.com/user-attachments/assets/65809135-98ee-4319-8931-bf9cb08bef61" />

        
- [ ]  **4. 회고를 잘 작성했나요?**
    - 배치사이즈 확대와 학습률 및 어텐션 헤드 조정, 그리고 sentencepiece 단어장 크기 화적화에 관련된 회고를 찾아 볼 수 있음
        - <img width="2082" height="1188" alt="image" src="https://github.com/user-attachments/assets/60f4afe6-a957-4e0b-8511-bf405af03f1a" />

        
- [ ]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수
    - 인코더 레이어와 디코더 레이어를 각각 독립된 nn.Module 클래스로 캡슐화한 뒤 nn.ModuleList를 통해 다중 레이어를 동적으로 생성하도록 설계하여 중복 코드를 완벽하게 제거
        - <img width="1208" height="1070" alt="image" src="https://github.com/user-attachments/assets/30c82e18-4081-40b8-a254-87aa5b33f959" />



# 회고(참고 링크 및 코드 개선)
```
- 전체적인 코드 창을 깔끔하고 보기 좋게 정리해 두셔서 가독성 최고였습니다.
- 마스킹이나 포지셔널 인코딩처럼 트랜스포머에서 저에게는 복잡하고 어려웠던 코드를 정석대로 작성하신 점과
- 문제의 원인이 코드의 논리적 오류가 아니라 '하이퍼파라미터 체급 문제'라는 것을 정확히 짚어내신 과정이 아주 인상깊었습니다!
```
