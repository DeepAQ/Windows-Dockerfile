FROM mcr.microsoft.com/windows/nanoserver:sac2016

ARG DOWNLOADURL=https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u202-b08/OpenJDK8U-jre_x64_windows_hotspot_8u202b08.zip

RUN powershell -Command \
    $ProgressPreference = 'SilentlyContinue'; \
    Invoke-WebRequest -Uri $env:DOWNLOADURL -OutFile 'C:\jre.zip'; \
    Expand-Archive -Path 'C:\jre.zip' -DestinationPath 'C:\'; \
    Remove-Item -Path 'C:\jre.zip' -Force; \
    $JreDir = Get-Item 'C:\jdk*'; \
    Rename-Item $JreDir -NewName 'C:\jre' -Force; \
    $env:PATH += ';C:\jre\bin'; \
    setx /m PATH $env:PATH

RUN java -version
