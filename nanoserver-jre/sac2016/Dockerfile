FROM mcr.microsoft.com/windows/nanoserver:sac2016

ARG DOWNLOADURL=https://repos.azul.com/azure-only/zulu/packages/zulu-8/8u202/zulu-8-azure-jre_8.36.0.3-8.0.202-win_x64.zip

RUN powershell -Command \
    $ProgressPreference = 'SilentlyContinue'; \
    Invoke-WebRequest -Uri $env:DOWNLOADURL -OutFile 'C:\zulu.zip'; \
    Expand-Archive -Path 'C:\zulu.zip' -DestinationPath 'C:\'; \
    Remove-Item -Path 'C:\zulu.zip' -Force; \
    $JreDir = Get-Item 'C:\zulu-*'; \
    Rename-Item $JreDir -NewName 'C:\jre' -Force; \
    $env:PATH += ';C:\jre\bin'; \
    setx /m PATH $env:PATH

RUN java -version
