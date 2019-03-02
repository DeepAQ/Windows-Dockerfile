FROM mcr.microsoft.com/windows/nanoserver:1809

ARG package=zulu8.36.0.1-ca-jdk8.0.202-win_x64

RUN \
    mkdir C:\jre && \
    curl -o C:\jre\zulu.zip https://cdn.azul.com/zulu/bin/%package%.zip && \
    tar -C C:\jre\ --strip-components 2 -xf C:\jre\zulu.zip %package%/jre && \
    del /f /q C:\jre\zulu.zip

ENV PATH="C:\Windows\system32;C:\Windows;C:\jre\bin"

RUN java -version
