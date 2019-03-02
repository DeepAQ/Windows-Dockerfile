FROM mcr.microsoft.com/windows/nanoserver:1809

ARG DOWNLOADURL=https://repos.azul.com/azure-only/zulu/packages/zulu-8/8u202/zulu-8-azure-jre_8.36.0.3-8.0.202-win_x64.zip

RUN \
    mkdir C:\jre\ && \
    curl -o C:\jre\zulu.zip %DOWNLOADURL% && \
    tar -C C:\jre\ --strip-components 1 -xf C:\jre\zulu.zip && \
    del /f /q C:\jre\zulu.zip

ENV PATH="C:\Windows\system32;C:\Windows;C:\jre\bin"

RUN java -version
