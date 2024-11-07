# ServerCloudRDPGoogleFree
Pengen server RDP VPS gratis di Google?

1. buatlah akun Google dulu,
2. kunjungi https://shell.cloud.google.com/?show=ide%2Cterminal lalu tempel di terminal

<pre>
<code id="code-block">
docker run -p 8070:80 dorowu/ubuntu-desktop-lxde-vnc
</code>
</pre>

3. lalu tunggu progress berikut :
<pre>
<code id="code-block">
Unable to find image 'dorowu/ubuntu-desktop-lxde-vnc:latest' locally
latest: Pulling from dorowu/ubuntu-desktop-lxde-vnc
a70d879fa598: Pull complete 
c4394a92d1f8: Pull complete 
10e6159c56c0: Pull complete 
6d516dea5dcb: Pull complete 
2c326a79b2c1: Extracting [==================================>                ]  104.7MB/152.1MB
77c398b95e39: Download complete 
1a5adfd9ff08: Download complete 
d8327acdb588: Download complete 
b4d11d536f7c: Download complete 
0403b18ddc74: Download complete 
c163d8624a71: Download complete 
1dc3570b5fa6: Download complete 
6f9c71cf3486: Download complete 
e02f721e36c7: Download complete 
ba596a49f65e: Download complete 
31c6cc0bdd8d: Download complete 
</code>
</pre>
sampai selesai pull (pull complete).

4. Setelah selesai pull terdapat :
<pre>
<code id="code-block">
2024-11-07 12:35:53,747 INFO Included extra file "/etc/supervisor/conf.d/supervisord.conf" during parsing
2024-11-07 12:35:53,753 INFO RPC interface 'supervisor' initialized
2024-11-07 12:35:53,753 CRIT Server 'unix_http_server' running without any HTTP authentication checking
2024-11-07 12:35:53,754 INFO supervisord started with pid 12
2024-11-07 12:35:54,757 INFO spawned: 'nginx' with pid 14
2024-11-07 12:35:54,762 INFO spawned: 'web' with pid 15
2024-11-07 12:35:54,766 INFO spawned: 'xvfb' with pid 16
2024-11-07 12:35:54,770 INFO spawned: 'wm' with pid 17
2024-11-07 12:35:54,774 INFO spawned: 'lxpanel' with pid 18
2024-11-07 12:35:54,778 INFO spawned: 'pcmanfm' with pid 19
2024-11-07 12:35:54,792 INFO spawned: 'x11vnc' with pid 20
2024-11-07 12:35:54,806 INFO spawned: 'novnc' with pid 21
2024-11-07 12:35:55,367 INFO  Listening on http://localhost:6079 (run.py:87)
2024-11-07 12:35:55,869 INFO success: nginx entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
2024-11-07 12:35:55,869 INFO success: web entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
2024-11-07 12:35:55,869 INFO success: xvfb entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
2024-11-07 12:35:55,869 INFO success: wm entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
2024-11-07 12:35:55,869 INFO success: lxpanel entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
2024-11-07 12:35:55,869 INFO success: pcmanfm entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
2024-11-07 12:35:55,869 INFO success: x11vnc entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
2024-11-07 12:35:55,869 INFO success: novnc entered RUNNING state, process has stayed up for > than 1 seconds (startsecs
</code>
</pre>

5. lalu Klik Web Preview, Change Port ke 8070 sesuai port yang ditulis di command tadi.
![b5b7922d-4630-48ef-bd40-6097be4ac42c](https://github.com/user-attachments/assets/0c6f5161-ffea-4a52-a633-223b9a6ad82d)
6. keluar tampilan environtment lxde basis Ubuntu 20 Focal dengan remot x11vnc
![34695734-fcd1-4f06-924a-b0c49a8e2aaa](https://github.com/user-attachments/assets/54fe60a0-9386-4309-bfe3-80e31e816c25)

# Konfigurasi & Update
1. Buka LXTerminal jalankan
<pre>
<code id="code-block">
rm  /etc/apt/sources.list.d/google-chrome.list
</code>
</pre>

2. Jalankan
<pre>
<code id="code-block">
vi /etc/apt/sources.list
</code>
</pre>
hapus repo sebelumnya, lalu salin dan tempel repo dari [sini](https://github.com/rafi-sudo/ServerCloudRDPGoogleFree/blob/3ede10d9c17e979df4c03dee365d0c72774d51aa/sources.list)

3. tutup editor vim CLI dengan Esc+:wq Enter
4. Lalu `sudo apt update` dan `sudo apt upgrade`
5. tunggu sampai seperti ini
![42b5d0f7-ba02-464c-be44-840666080278](https://github.com/user-attachments/assets/e75d81d9-cc9c-4ad3-8e8e-66138b962676)
![5a8660f8-fdb8-4f61-b6e7-dbea0eb533c6](https://github.com/user-attachments/assets/dcf689d0-c627-4c0c-8196-669fa3cf9e5a)

6. Ketik Y di keyboard
7. lalu tunggu mengupgrade dari repo tadi,
8. Setelah selesai di update, maka server RDP VPS siap dipakai .



