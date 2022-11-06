# Ansible-Playground

### このRepositoryについて

Ansibleを学習するためのPlayground環境です

### 使い方

```
cd docker
docker-compose exec control-node bash
cd ansible
ansible-playbook -i test (インベントリファイル) setup-web-server.yml (プレイブックファイル)
```
