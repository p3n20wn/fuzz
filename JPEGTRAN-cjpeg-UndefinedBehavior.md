# Details
 ![image](https://github.com/user-attachments/assets/9d8b40a7-b97b-4fdc-ad8d-cd1231ee2c1e)

```bash
➜  bin ls
c1  cjpeg  djpeg  jpegtran  rdjpgcom  wrjpgcom
➜  bihexdump -C c1
00000000  50 32 32 32 13 32 32 32  50 32 32 50 32 32 32 32  |P222.222P22P2222|
00000010  32 32 32 00 00 32 32 89  2e                       |222..22..|
00000019
➜  bin ./cjpeg ./c1
UndefinedBehaviorSanitizer:DEADLYSIGNAL
==121022==ERROR: UndefinedBehaviorSanitizer: SEGV on unknown address 0x00004048897e (pc 0x000000426add bp 0x000040268398 sp 0x7ffd8e970d10 T121022)
==121022==The signal is caused by a READ memory access.
    #0 0x426add in get_text_gray_row /home/n0zom1z0/fuzzing_JPEG/jpegtran-master/rdppm.c:153:14
    #1 0x42532a in main /home/n0zom1z0/fuzzing_JPEG/jpegtran-master/cjpeg.c:642:21
    #2 0x7fddeb99c082 in __libc_start_main /build/glibc-LcI20x/glibc-2.31/csu/../csu/libc-start.c:308:16
    #3 0x40464d in _start (/home/n0zom1z0/fuzzing_JPEG/install/bin/cjpeg+0x40464d)

UndefinedBehaviorSanitizer can not provide additional info.
SUMMARY: UndefinedBehaviorSanitizer: SEGV /home/n0zom1z0/fuzzing_JPEG/jpegtran-master/rdppm.c:153:14 in get_text_gray_row
==121022==ABORTING
```

`c1` file can be downloaded here: https://drive.google.com/file/d/1lLe6UGf2y-jZG7foTutxRnvSlwh9J4gk/view
