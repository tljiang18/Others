FROM ecr.vip.ebayc3.com/krylov/krylov-workspace-jupyter:cuda10.1-cudnn7-py3.6-ubuntu18.04-base

RUN apt update

RUN yes | apt install build-essential

RUN apt-get -y install unixodbc unixodbc-dev 

RUN curl http://installsvc.vip.ebay.com/packages/carmel/ODBC/RELEASE/0.1.10/Linux/carmel-0.1.10.deb -o carmel-0.1.10.deb

RUN dpkg -i carmel-0.1.10.deb

RUN conda update conda

RUN pip install pyodbc

COPY odbc.ini /etc/odbc.ini

COPY odbcinst.ini /etc/odbcinst.ini

RUN chmod 755 /opt/simba/carmel/libSparkODBC64.so

RUN chmod 755 /opt/simba/carmel/libcpasswordsdk.so

RUN rm -R /opt/conda/pkgs/pyyaml-5.2*



