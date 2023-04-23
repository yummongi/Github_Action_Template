# Github_Action_Template

동적 원리
1. main.yml에서 with 절의 num 값이 11로 설정되고, `uses: ./`를 통해 action.yml로 num 값과 함께 이동합니다.
2. action.yml에서 inputs의 num 값은 기본값이 1로 설정되어 있지만, main.yml에서 지정한 11로 변경되어 num 값은 11이 됩니다.
3. action.yml의 outputs 단계는 워크플로우에서 action.yml의 outputs인 num_squared를 사용할 수 있게 해줍니다.
4. composite 유형을 통해 작업이 한꺼번에 진행되며, Python 3.10 버전 설치와 Python 의존성 설치가 진행됩니다.
5. GITHUB의 환경변수에 inputs 단계의 num (11)을 INPUT_NUM 이름으로 설정하여 값을 저장합니다.
6. src 파일의 get_num_square.py 파이썬 파일이 실행됩니다.
7. get_num_square.py에서 환경변수 INPUT_NUM의 11 값을 num 변수로 저장하여 int 타입으로 변환한 후, action.yml의 output의 num_squared에 num의 제곱값을 저장합니다.
8. workflows main.yml 파일의 "Print the square"의 run 부분이 실행되어, action.yml에 output의 num_squared에 저장된 num 값이 출력됩니다.
