# 배포할 때마다 Timezone kst 로 setup 하기
  - .ebextensions의 config 파일에 아래와 같이 설정하면 된다.
    ```
    commands:
      set_time_zone:
        command: ln -f -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime
    ```