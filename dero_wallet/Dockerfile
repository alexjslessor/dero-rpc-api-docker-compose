FROM ubuntu:18.04


WORKDIR $HOME/backend

RUN apt-get update
#RUN apt-get update && apt-get install -y wget sudo
#RUN wget https://github.com/deroproject/derosuite/releases/download/Version_P2P_bug_fix/dero_linux_amd64_2.2.1-0.Atlantis.Astrobwt+03072020.tar.gz -O - | tar --strip-components 2 -C /opt/ -xzf -

# COPY ./mainnet ./mainnet
COPY ./dero-wallet-cli-linux-amd64 ./
COPY ./wallet.db ./
