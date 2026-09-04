FROM quantconnect/lean:latest

USER root

COPY HanmiBuyAndHold.py /module/HanmiBuyAndHold.py
COPY download_hanmi_data.py /module/download_hanmi_data.py
COPY config.json /module/config.json
COPY entrypoint.sh /module/entrypoint.sh

RUN chmod +x /module/entrypoint.sh \
    && mkdir -p /results

ENTRYPOINT ["/module/entrypoint.sh"]
