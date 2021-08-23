FROM watermelon
MAINTAINER w1
COPY . /app
RUN cd /app;\
    go env -w GOPROXY=https://goproxy.cn,direct; \
    CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build  -o ./test ./main.go; \


FROM watermelon
ENV XTHK_CODE_ROOT=/var/www/code/app
COPY --from=0 /app/live_api_pub ${XTHK_CODE_ROOT}/test

WORKDIR /var/www/code/app
CMD ["/var/www/code/app/test"]
