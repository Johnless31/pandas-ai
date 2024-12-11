- git clone git@github.com:Johnless31/pandas-ai.git/
- cd pandas-ai
- cp client/.env.example client/.env
- cp server/.env.example server/.env
- 在server/.env文件中，填上你的key；代理地址填写正确（能直连墙外的可以删掉代理配置HTTP_PROXY，HTTPS_PROXY，NO_PROXY）
- 在client/.env文件中，将NEXT_PUBLIC_API_URL的ip填写正确，写server端所在机器的公网ip，因为js要靠该地址与后端交互
- docker-compose -f ./docker-compose-host.yaml build // 一定要先改写好env文件在编译
- docker-compose -f ./docker-compose-host.yaml up -d

### 注意事项
在构建镜像过程中，若要使用代理，要记得及时清除代理
- ENV http_proxy http://proxy.example.com:8080
- ENV https_proxy http://proxy.example.com:8080
- 其他构建指令
- RUN unset http_proxy https_proxy
