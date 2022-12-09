WEB版本：

docker run \
  -ti --rm \
  --name=techxuexi-web \
  --shm-size="2g" \
  -e "ZhuanXiang=True" \
  -e "Pushmode=6" \
  -p "9988:80" \
  -v "/xxqg/xuexi:/xuexi/user" \
  docker.mirror.aliyuncs.com/techxuexi/techxuexi-amd64
  
  # 在前面加 docker.mirror.aliyuncs.com 可以更快速拉取镜像
  # 不指定TAG，docker会默认使用 lates


微信版本：

docker run \
  -ti --rm \
  --name=techxuexi-WeChat \
  --shm-size="2g" \
  -e "ZhuanXiang=True" \
  -e "Pushmode=2" \
-e "Scheme=dtxuexi://appclient/page/study_feeds?url=" \
  -p "9966:8088" \
  -v "/root/xuexi-2:/xuexi/user" \
  docker.mirror.aliyuncs.com/techxuexi/techxuexi-amd64
  
  # 在前面加 docker.mirror.aliyuncs.com 可以更快速拉取镜像
  # 不指定TAG，docker会默认使用 lates




专项答题开启：

def weekly(cookies, scores, driver_default=None):
    quiz_type = "weekly"
    score_all = const.weekly_all
    quiz_xpath = '//*[@id="app"]/div/div[2]/div/div[3]/div[2]/div[7]/div[2]/div[2]/div' 
    category_xpath = '//*[@id="app"]/div/div[2]/div/div[4]/div[1]/div[1]'
    answer_question(quiz_type, cookies, scores, score_all,
                    quiz_xpath, category_xpath, driver_default=driver_default)


def zhuanxiang(cookies, scores, driver_default=None):
    quiz_type = "zhuanxiang"
    score_all = const.zhuanxiang_all
    quiz_xpath = '//*[@id="app"]/div/div[2]/div/div[3]/div[2]/div[6]/div[2]/div[2]/div'
    category_xpath = '//*[@id="app"]/div/div[2]/div/div[6]/div[1]/div[1]'
    answer_question(quiz_type, cookies, scores, score_all,
                    quiz_xpath, category_xpath, driver_default=driver_default)

滑块解决：

Chromedriver去滑块下载地址：
https://github.com/kiko923/backup/tree/main/%E7%A7%91%E6%8A%80%E5%BC%BA%E5%9B%BD

目录： /xuexi/  替换chromedriver文件

然后去改 /xuexi/pdlearn/mydriver.py 这个文件
取消注释swiper_valid()
注释pushprint()


下载以下工具并解压：
(win环境工具) 下载地址: https://pan.baidu.com/s/1SnmXcCSeE2YT3Z8-Hey7yA 提取码 : wat7
在解压完的目录里找到wxmedit.exe 并用wxmedit.exe 打开 chromedriver.exe
搜索$cdc

把cdc替换成abc，替换完成一定要 保存！


进目录 添加权限chmod +775 chromedriver





1. 清空所有的 iptables chains

sudo iptables -t filter -F
sudo iptables -t filter -X
2. 重启 docker 服务即可

复制
sudo systemctl restart docker
