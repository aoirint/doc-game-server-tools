# doc-game-server-tools

ゲームサーバ関連ツールドキュメント

## ARK: Survival Evolved (n0la/rcon)

[GitHub](https://github.com/aoirint/rcon-docker) [Docker Hub](https://hub.docker.com/r/aoirint/rcon) [Source](https://github.com/n0la/rcon)

```shell
docker run --rm --network host aoirint/rcon:20220806.1 rcon -H 127.0.0.1 -p 27020 -P "${ADMIN_PASSWORD}" --minecraft MyServerCommand

# [ARK: Survival Evolved] ListPlayers
docker run --rm --network host aoirint/rcon:20220806.1 rcon -H 127.0.0.1 -p 27020 -P "${ADMIN_PASSWORD}" --minecraft ListPlayers
```

## Minecraft (py-mine/mcstatus)

[GitHub](https://github.com/aoirint/mcstatus-docker) [Docker Hub](https://hub.docker.com/r/aoirint/mcstatus) [Source](https://github.com/py-mine/mcstatus)

### Jave Edition

```shell
docker run --rm --network host aoirint/mcstatus:20220818.1 "127.0.0.1:25565" status
```

### Bedrock Edition

- [py-mine/mcstatus#301](https://github.com/py-mine/mcstatus/issues/301): CLI doesn't support Bedrock Servers

```shell
docker run --rm --network host --entrypoint "" aoirint/mcstatus:20220818.1 gosu user python3 -c 'from mcstatus import MinecraftBedrockServer; print(MinecraftBedrockServer.lookup("127.0.0.1:19132").status().players_online)'
```
