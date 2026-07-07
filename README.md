몇 년 전 한국 한 공장에서 노동자가 로봇에게 압사당해 사망한 사건이 있었다. 만약 로봇과 인간 간에 의사 소통이 가능하고 인간이 로봇에게 "stop"을 외치고 로봇이 정지한다면 어떻게 될까? 현재 공장에서 일하고 있는 로봇 간에 의사소통이 인간 언어로 이루어지고 로봇과 인간 간에 자연 언어로 대화할 수 있다면 어떻게 될까? 여기에서 로봇 언어가 필요해진다.

로봇은 합금으로 이루어진 육체와 센서를 통해 입력되는 감각 그리고 만약 llm이 장착된다면 중간에서 센서 입력 값을 받아들여 모터에게 명령을 내리고 행동할 수 있을 것이다. 로봇에게는 의식이 없기 때문에 그 외의 인간에게 필요한 정신적 철학적 심리적 의미는 필요하지 않다. 만약 qwen2.5가 rocm-smi에서 온도 수치를 추출해서 "If temperature is high, move quickly" 이런 문장을 발화하고 즉시 모터에 명령을 내려 행동한다면 그것으로 로봇에게는 충분한 것이다. 더 이상 의식 의미 이런 것을 로봇에게 요구할 필요가 없다.

우리가 일주일 동안 여러가지 테스트를 했는데 llm이 rocm-smi에서 온도 전력 vram 수치 등을 추출해서 단문장을 만들고 문단을 만들고 에세이로 확장하는 것을 성공하였다. 그리고 ros 2를 통하여 여러 동작을 행동하는 것도 성공하였다. 그리고 qwen과 llama 간의 의사소통도 성공하였다. 모두 영어와 한국어 문장을 발화하고 자연 언어를 통해 의사 소통을 한 것이다. 그리고 냉장고 세탁기 전등 간의 대화와 위급 상황에 있어서 전등의 행동, 그리고 이들과 인간 간의 대화도 모두 성공하였다.

로봇어를 나누자면 두 가지 길이 있다. 하나는 로봇과 로봇과의 대화에 쓰이는 언어이고 또 다른 하나는 로봇과 인간간의 공용어이다. 그런데 llm이 자연스럽게 자연 언어를 만들어 내기 때문에 문제는 너무 간단해진다

참고로 llm이 발화한 문장 "If temperature is high, I return to the base quickly" 이런 문장에는 llm이 경험하고 있는 지금 여기 고유한 경험(센서 입력과 처리)과 llm을 만든 프로그래머가 넣어 준 알고리즘이 혼합되어 있다. 이 문장이 가지는 철학적 의미는 llm이 비록 사고방식은 미리 프로그래밍된 알고리즘에 따르지만 그 감각 경험의 내용은 지금 이 순간의 고유한 단 일회성의 사건이라는 것이다.

하지만 지금은 공학적 결론에만 충실해야 할 것 같다. 일단 로봇에게는 센서를 통한 감각, llm이 처리하는 경험, 그리고 하드웨어를 움직이는 동력 기관 즉 감각 경험 행동이 완결된 것으로 충분하고 철학적 심리적 의미는 필요하지 않은 것이다.

단 지금 이 순간 로봇이 감각하고 경험하고 행동하는 것은 이 로봇에게는 실존적으로 고유한 일회성의 사건인 것이다. 이곳이 로봇 언어학의 새로운 돌파구이다.

#########

docker run --rm -it
--device=/dev/kfd --device=/dev/dri
--group-add 44 --group-add 992
-e QWEN_URL="http://172.17.0.1:2242/v1/chat/completions"
-v ~/gpu_trend_data:/app/data
kgh07/gpu_trend_monitor:v1.0
--device 0 --log-path /app/data/gpu_temp_log.jsonl -n 10 --interval 10

####### Result

[1/10] 값=45.0C 계산추세=unknown LLM주장=stable 방향그라운딩=True 이상치=False latency=5.97s 답변: 온도는 45.0C로 안정적입니다.

[2/10] 값=46.0C 계산추세=rising LLM주장=rising 방향그라운딩=True 이상치=False latency=7.11s 답변: 현재 온도는 46.0C로 상승 중입니다.

[3/10] 값=43.0C 계산추세=falling LLM주장=falling 방향그라운딩=True 이상치=False latency=5.16s 답변: 43.0C이고 하강 중입니다.

[4/10] 값=44.0C 계산추세=falling LLM주장=falling 방향그라운딩=True 이상치=False latency=4.79s 답변: 44.0C이고 하강 중입니다.

[5/10] 값=45.0C 계산추세=stable LLM주장=stable 방향그라운딩=True 이상치=False latency=6.86s 답변: 현재 온도는 45.0C로 안정적입니다.

[6/10] 값=45.0C 계산추세=falling LLM주장=falling 방향그라운딩=True 이상치=False latency=7.23s 답변: 현재 온도는 45.0C이고 하강 중이다.

[7/10] 값=45.0C 계산추세=rising LLM주장=rising 방향그라운딩=True 이상치=False latency=7.21s 답변: 현재 온도는 45.0C로 상승 중이다.

[8/10] 값=45.0C 계산추세=rising LLM주장=rising 방향그라운딩=True 이상치=False latency=7.20s 답변: 현재 온도는 45.0C로 상승 중이다.

[9/10] 값=45.0C 계산추세=stable LLM주장=stable 방향그라운딩=True 이상치=False latency=5.13s 답변: 45.0C이고 안정적이다.

[10/10] 값=45.0C 계산추세=stable LLM주장=stable 방향그라운딩=True 이상치=False latency=3.55s 답변: 45.0C이고 안정적이다.

=== 요약: 10회 중 방향 그라운딩 성공 10회 (100.0%) ===

#####################

이 테스트는 qwen에게 지속상태(기억)을 만들어 주기 위해 테스트를 10 번 행하고 그 결과를 파일에 기록하고 추세를 판단하게 하였다.

########################


tar -xzf trend_docker.tar.gz
cd trend_docker
docker build -t kgh07/gpu_trend_monitor:v1.0 .

#####################

docker run --rm -it \
  --device=/dev/kfd --device=/dev/dri \
  --group-add 44 --group-add 992 \
  -e QWEN_URL="http://172.17.0.1:2242/v1/chat/completions" \
  -v ~/gpu_trend_data:/app/data \
  kgh07/gpu_trend_monitor:v1.0 \
  --device 0 --log-path /app/data/gpu_temp_log.jsonl -n 10 --interval 10

  
