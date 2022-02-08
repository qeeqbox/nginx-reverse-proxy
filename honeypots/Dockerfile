FROM python:3.7
WORKDIR /app
#RUN pip install honeypots
COPY . .
RUN cd honeypots && python3 setup.py sdist bdist_wheel && pip3 install .
CMD ["sh","-c","python3 -m honeypots --setup http:80 --termination-strategy signal"]
