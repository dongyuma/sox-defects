# Affected Version
mupdf 1.23.4

# Vulnerability Description
floating point exception (divide-by-zero) issues was discovered in mupdf 

# mupdf download address
https://github.com/ArtifexSoftware/mupdf

## 1. A floating point exception (divide-by-zero) issue was discovered in mupdf in functon bmp_decompress_rle4() of load-bmp.c in line 541.

![image](https://github.com/dongyuma/sox-defects/assets/87286944/06cabb87-15d6-4396-97ce-06d93454cfeb)
![image](https://github.com/dongyuma/sox-defects/assets/87286944/726ff82c-1c59-452d-9495-25b25a8cfb43)

## 2. A floating point exception (divide-by-zero) issue was discovered in mupdf in functon fz_new_pixmap_from_float_data() of pixmap.c in line 1330.

![image](https://github.com/dongyuma/sox-defects/assets/87286944/5e18c772-474d-44e4-a53a-ed9980c6d3c0)

## 3. A floating point exception (divide-by-zero) issue was discovered in mupdf in functon compute_color() of jquant2.c in line 533.

![image](https://github.com/dongyuma/sox-defects/assets/87286944/1a1c7bfd-059e-4e69-b044-9fed2de9d26d)
![image](https://github.com/dongyuma/sox-defects/assets/87286944/2beb34ce-37e2-43c0-8da5-0e52957e151a)
![image](https://github.com/dongyuma/sox-defects/assets/87286944/e7a27960-81c6-4334-846a-e4208fc6bbf9)

## 4. A floating point exception (divide-by-zero) issue was discovered in mupdf in functon pnm_binary_read_image() of load-pnm.c in line 519.

![image](https://github.com/dongyuma/sox-defects/assets/87286944/ad8b0e05-a74c-4c8f-bdf9-718bf6607231)
![image](https://github.com/dongyuma/sox-defects/assets/87286944/c1e3c390-b523-4b36-bdb2-0c80dc377b07)

## 5. A floating point exception (divide-by-zero) issue was discovered in mupdf in functon pnm_binary_read_image() of load-pnm.c in line 527.

![image](https://github.com/dongyuma/sox-defects/assets/87286944/ca9af87d-247e-4f4d-b451-6839a3bccf37)
