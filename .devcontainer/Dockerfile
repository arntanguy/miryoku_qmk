FROM mcr.microsoft.com/devcontainers/cpp:ubuntu-22.04

RUN export DEBIAN_FRONTEND=noninteractive

RUN apt update && apt install -y --no-install-recommends git python3-pip
RUN python3 -m pip install qmk

USER vscode

RUN qmk setup -y
RUN echo 'echo "To build use: qmk compile -c -kb crkbd/rev1 -km manna-harbour_miryoku -e MIRYOKU_ALPHAS=QWERTY -e MIRYOKU_NAV=VI -e MIRYOKU_EXTRA=COLEMAKDH -e MIRYOKU_TAP=QWERTY -e CONVERT_TO=rp2040_ce"' > ~/.bashrc

ENTRYPOINT ["/bin/bash", "-c"]
