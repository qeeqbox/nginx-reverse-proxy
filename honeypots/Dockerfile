FROM python:3.7
WORKDIR /app
RUN pip install honeypots==0.48
CMD ["sh","-c","python3 -m honeypots --setup http:80 --termination-strategy signal"]
