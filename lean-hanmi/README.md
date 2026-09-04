# 한미반도체 LEAN Docker 모듈

`quantconnect/lean` 기반의 독립 실행 이미지입니다. 시작 시 Yahoo Finance의
한미반도체 보통주(`042700.KS`) 일봉을 받아 Custom Data로 읽고, 첫 데이터 시점에
1주 매수 주문을 내는 Buy & Hold 백테스트를 수행합니다.

저장소 루트에서 다음처럼 실행합니다.

```bash
docker compose -f docker-compose.hanmi.yml run --rm hanmi-backtest
```

기본 기간은 2024년이며 환경 변수로 변경할 수 있습니다.

```bash
HANMI_START_DATE=2023-01-01 HANMI_END_DATE=2024-01-01 \
  docker compose -f docker-compose.hanmi.yml run --rm hanmi-backtest
```

이 전략은 주문 흐름 검증용 예제입니다. KRX 거래비용·세금·배당·액면분할,
환율·슬리피지는 반영하지 않으므로 정확한 실거래 성과 분석에 사용하면 안 됩니다.