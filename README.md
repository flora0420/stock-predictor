---
title: StockPredictor
emoji: 🌍
colorFrom: red
colorTo: green
sdk: docker
pinned: false
license: mit
---

Check out the configuration reference at https://huggingface.co/docs/hub/spaces-config-reference


# Stock Prophet

A demo for stock prophet deployment on huggingface spaces

## Usage
```
curl localhost:8000/ping

curl \
--header "Content-Type: application/json" \
--request POST \
--data '{"ticker":"MSFT", "days":7}' \
http://localhost:8000/predict
```

## docker setup 
docker run -d --rm --name mycontainer -p 8000:8000 stock-prophet
```
docker images # docker rmi or docker image prune
docker build -t stock-neuralprophet .
docker run -p 8000:8000 stock-neuralprophet  # one can see the log
docker run -d --rm --name mycontainer -p 8000:8000 stock-neuralprophet   # behind the scene
```

## Side note about SSH with HF spaces for the first time
Assume that you've already set up your ssh key and added it to your github account. Now you will need to add it to your HF spaces account. 

At this point, you shall have a HuggingFace account.

You shall already have a ssh keypair, say `id_25519` and `id_25519.pub` in `~/.ssh`. If not, you can generate one by `ssh-keygen -t ed25519 -C "your.email@example.co"

Add it to your SSH agent with ssh-add ( [ref](https://huggingface.co/docs/hub/security-git-ssh) ): 
```
ssh-add ~/.ssh/id_ed25519
```

- Add the SSH public key to your HuggingFace account by running:
```
cd ~/.ssh
cat id_25519.pub
```
and copy the content to Settings > SSH and GPG keys > Add SSH key


- Testing your SSH authentication
```
ssh -T git@hf.co
```
and make sure the message reads `Hi hf_username, welcome to Hugging Face.`

- Clone the repo from a space:
```
git clone git@hf.co:spaces/<username>/<repo>
```