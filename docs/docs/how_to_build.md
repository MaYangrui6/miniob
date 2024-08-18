---
title: 濡備綍缂栬瘧
---

# 濡備綍缂栬瘧

## 0. base

鍋囪绯荤粺涓婂凡缁忓畨瑁呬簡make绛夌紪璇戝伐鍏枫�??

MiniOB 闇€瑕佷娇鐢細

- cmake 鐗堟�? >= 3.13
- gcc/clang gcc 11 浠ヤ笂锛宑lang 14浠ヤ笂锛岀紪璇戝櫒闇€瑕佹敮鎸�?++20鏂版爣鍑?
- flex (2.5+), bison (3.7+) 鐀��簬鐢熸垚璇嶆硶璇硶鍒嗘瀽浠ｇ爜

## 1. 鐜鍒濆�??

濡傛灉鏄涓€娆″湪杩欎釜鐜涓婄紪璇憁iniob锛岄渶瑕佸畨瑁呬竴浜沵iniob鐨勪緷璧栧簱锛屾墽琛屼笅闈㈢殑鍛戒护鍗冲彲瀹夎锛?

```bash
bash build.sh init
```

鑴氭湰灏嗚嚜鍔ㄦ媺鍙栦緷璧栧�?(鍙互鍙傝€? .gitmodules) 鐒跺悗缂栬瘧瀹夎鍒扮郴缁熺洰褰曘€?

濡傛灉鎵ц鐢ㄦ埛涓嶆槸root锛岄渶瑕佸湪鍛戒护鍓嶅姞�?? `sudo`�??

```bash
sudo bash build.sh init
```

> 濡傛灉浣跨敤 GitPod 寮€鍙戯紝鍙互璺宠繃杩欐锛屼細鑷姩鎵ц�??

## 2. 缂栬�?

鎵ц涓嬮潰鐨勫懡浠ゅ嵆鍙畬鎴愮紪璇戯細

```bash
bash build.sh
```

姝ゅ懡浠ゅ皢缂栬瘧涓€涓狣EBUG鐗堟湰鐨刴iniob銆傚鏋滃笇鏈涚紪璇戝叾瀹冪増鏈殑锛屽彲浠ュ弬�?? `bash build.sh -h`锛屾瘮濡傦細

```bash
bash build.sh release
```

姝ゅ懡浠ゅ皢缂栬瘧release鐗堟湰鐨刴iniob�??

## 3. 杩愯�?

鍙傝�?? [濡備綍杩愯](how_to_run.md)

## FAQ

### 1. sudo鎵句笉鍒癱make

**Q:**

鍦ㄢ�??1. 鐜鍒濆鍖栤€濅腑鎵ц鍛戒护:

```bash
sudo bash build.sh init
```

鏃讹紝鎶ラ敊:

```bash
build.sh: line xx: cmake: command not found
```

**A:**

- 1. 妫€鏌モ�??0. base鈥濅腑cmake鐗堟湰瑕佹眰鏄惁婊¤冻銆?

```bash
cmake --version
```

- 2. 妫€鏌ユ槸鍚﹀嚭鐜颁簡鈥淟inux绯荤粺涓嬫墽琛宻udo鍛戒护鐜鍙橀噺澶辨晥鐜拌薄鈥濄€?

***妫€�??***

鍦ㄥ綋鍓嶇敤鎴峰拰root鐀��埛涓嬪潎鑳芥壘鍒癱make锛岃€屽湪褰撳墠鐀��埛涓媠udo cmake鍗存壘涓嶅埌cmake锛屽�?:

```bash
[mu@vm-cnt8:~]$ sudo -E cmake --version
[sudo] password for mu: 
sudo: cmake: command not found
```

鍒欏彲鑳藉氨鍑虹幇浜嗏€淟inux绯荤粺涓嬫墽琛宻udo鍛戒护鐜鍙橀噺澶辨晥鐜拌薄鈥濓紝鏈緥涓叿浣撴槸PATH鐜鍙橀噺瀹炴晥锛堣閲嶇疆锛夛紝瀵艰嚧鎵句笉鍒癱make�??

***瑙ｅ喅鏂规硶锛氬缓绔嬭蒋閾炬�?***

- 鎵惧埌鎵цsudo鍛戒护鏃剁殑PATH鍙橀噺涓湁鍝簺璺緞�??

```bash
[mu@vm-cnt8:~]$ sudo env | grep PATH
PATH=/sbin:/bin:/usr/sbin:/usr/bin
```

- 鎵惧埌cmake鎵€鍦ㄧ殑璺緞�??

```bash
[mu@vm-cnt8:~]$ whereis cmake
cmake: /usr/local/bin/cmake /usr/share/cmake
```

- 鍦≒ATH鍙橀噺涓殑涓€涓悎閫傝矾寰勪笅寤虹珛鎸囧悜cmake鐨勮蒋閾炬帴�??

```bash
[root@vm-cnt8:~]# ls /usr/bin | grep cmake
[root@vm-cnt8:~]# ln -s /usr/local/bin/cmake /usr/bin/cmake
[root@vm-cnt8:~]# ll /usr/bin | grep cmake
lrwxrwxrwx. 1 root root          20 Sep  1 05:57 cmake -> /usr/local/bin/cmake
```

***楠岃�?***

```bash
$ sudo -E cmake --version
cmake version 3.27.4
```

鍙戠幇sudo鏃惰兘鎵惧埌cmake浜嗭紝姝ゆ椂鍐嶆墽琛?

```bash
sudo bash build.sh init
```

鍒欎笉浼氬洜涓烘壘涓嶅埌cmake鑰屾姤閿欍€?

**鏇村淇℃伅�??**

鍏充簬璇ラ棶棰樼殑鏇村缁嗚妭锛岃鍙傝€僛闂鏉ユ簮](https://ask.oceanbase.com/t/topic/35604437/7)�??
鍏充簬璇ラ棶棰樼殑杩涗竴姝ュ垎鏋愶紝璇峰弬鑰僛Linux绯荤粺涓嬫墽琛宻udo鍛戒护鐜鍙橀噺澶辨晥鐜拌薄](https://zhuanlan.zhihu.com/p/669332689)�??
涔熷彲浠ュ皢cmake鎵€鍦ㄨ矾寰勬坊鍔犲埌sudo鐨凱ATH鍙橀噺涓潵瑙ｅ喅涓婅堪闂锛岃鍙傝€僛sudo鍛戒护涓嬬幆澧冨彉閲忓疄鏁堢殑瑙ｅ喅鏂规硶](https://www.cnblogs.com/xiao-xiaoyang/p/17444600.html)�??
