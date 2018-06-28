# Usage

## 対象サーバー

```
$ sudo yum install ansible -y
```

## ローカル

```
$ cp hosts.sample hosts
$ vi hosts
```
IPアドレスとpemファイルの名前を修正


### Ping

実行前にサーバーにアクセスできるか確認

```
$ ansible ec2 -i hosts -m ping
```

問題なければ以下が返ってくる。

```
111.1111.111.111 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

### playbookで実行されるタスク確認

```
$ ansible-playbook init.yml -i hosts --list-tasks
```

### playbookのdry run

```
$ ansible-playbook init.yml -i hosts --check
```

### playbook実行

