FROM mcr.microsoft.com/windows/nanoserver:1809

ARG DOWNLOADURL=https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u202-b08/OpenJDK8U-jre_x64_windows_hotspot_8u202b08.zip

RUN \
    mkdir C:\jre\ && \
    curl -o C:\jre\jre.zip %DOWNLOADURL% && \
    tar -C C:\jre\ --strip-components 1 -xf C:\jre\jre.zip && \
    del /f /q C:\jre\jre.zip

ENV PATH="C:\Windows\system32;C:\Windows;C:\jre\bin"

RUN java -version
