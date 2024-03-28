# Titan-Network-Cli-Node
Titan Network Cli Node Kurulumu, 
Donanım özellikleri çok düşük, 
(CPU 1 core & above  -  Memory 0.5GB & above - Disk 1G & above)

-Herhangi docker kurulu bir nodun yanına kurulabilir
1.Adımı geçip 2.Adımdan başlayın

-Docker kurulumu yoksa 1. adımdan başlayınız.

## 1. Adım Güncelleme ve docker kurulumu, komutları sırasıyla girebilirsiniz
```console
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# bu komut satırını toplu girebilirsiniz
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# docker güncelleme ve run
sudo apt update -y && sudo apt upgrade -y
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo docker run hello-world
```

## 2.Adım KURULUMA GEÇİN
```console
docker pull nezha123/titan-edge

mkdir ~/.titanedge

docker run -d -v ~/.titanedge:/root/.titanedge nezha123/titan-edge
# (çıktısında uzun bir id verecek onu not alın)

docker exec -it <id> /bin/bash
# (yukarda not aldığınız id yi tırnakları kaldırıp koddaki <id> yazan yere yapıştırın)
```

https://test1.titannet.io/login   
 Siteye gidip Kayıt olun, giriş yapın. Sırasıyla Resimlerdeki işlemleri yapın, en sonda identity code not alın.  

```console
titan-edge bind --hash=<identitycode> https://api-test1.container1.titannet.io/api/v2/device/binding
```
(Son olarak aldığınız identity codu, kodda ilgili yere yapıştırın.)


![image](https://titannet.gitbook.io/~gitbook/image?url=https:%2F%2F3087894035-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F6MWUoQBijnrc0tNWtAzG%252Fuploads%252FxgRYWGWdkb3vWIP6uATt%252Fimage.png%3Falt=media%26token=fde127bd-231e-49c8-a645-ce693aee7d8b&width=768&dpr=4&quality=100&sign=96cc55ad280fc4be09808bc5e6742a033b92b5e7fdb0661a99ca00acfc8d70d4)

![image](https://titannet.gitbook.io/~gitbook/image?url=https:%2F%2F3087894035-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F6MWUoQBijnrc0tNWtAzG%252Fuploads%252F49Uk9iZn2imNHCgUv2jr%252Fimage.png%3Falt=media%26token=52da5a45-04b3-4bf0-9b50-bf5ea9a2d003&width=768&dpr=4&quality=100&sign=7d81f84f31ca182cc5d5a9f62541839c82afe7620f7f0c30769a2c35c4952c93)

![image](https://titannet.gitbook.io/~gitbook/image?url=https:%2F%2F3087894035-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F6MWUoQBijnrc0tNWtAzG%252Fuploads%252FfjICpV8sEww91qT8p7R3%252Fimage.png%3Falt=media%26token=145e68c8-6b5e-47cc-8a13-676b248f5e09&width=768&dpr=4&quality=100&sign=7349d065e33c000fbf795f16571bdd6cec5fda9bb8ace1ce478b9e116eabd2e1)


![image](https://titannet.gitbook.io/~gitbook/image?url=https:%2F%2F3087894035-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F6MWUoQBijnrc0tNWtAzG%252Fuploads%252FLOITMfMIbxSKvxUnlPLY%252Fimage.png%3Falt=media%26token=cec9660c-de3b-4801-840d-8c7d500fc60f&width=768&dpr=4&quality=100&sign=83aa71cc15f46fa19567bdcdc258db7ee7e847e003cc1dced06094a945fedf23)
