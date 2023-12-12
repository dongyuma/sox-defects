# Affected Version
SoX（Sound eXchange） 14.4.2

# Vulnerability Description
floating point exception (divide-by-zero) issues was discovered in SoX 

# Sox download address
https://github.com/chirlu/sox


# Vulnerability Details

## 1. A floating point exception (divide-by-zero) issue was discovered in SoX in functon flowTrigger() of vad.c file in line 258.
![image](https://github.com/dongyuma/sox-defects/assets/87286944/a254286e-f2a6-465e-b710-54a3a423b774)
![image](https://github.com/dongyuma/sox-defects/assets/87286944/388ece04-5b43-4e57-aa29-55de744a36a2)

## 2. A floating point exception (divide-by-zero) issue was discovered in SoX in functon dcbias_() of dcbias.c file in line 73.
![image](https://github.com/dongyuma/sox-defects/assets/87286944/9e725a07-3878-4127-82a1-80dc1015aade)
![image](https://github.com/dongyuma/sox-defects/assets/87286944/affca2c8-e947-42e1-9159-2919ccb4ee07)

## 3. A floating point exception (divide-by-zero) issue was discovered in SoX in functon sox_read_wide() of sox.c file in line 489.
![image](https://github.com/dongyuma/sox-defects/assets/87286944/9a0e7aeb-811d-45ec-8cae-43e90202f57e)
![image](https://github.com/dongyuma/sox-defects/assets/87286944/f933a697-effc-4277-b682-31b191d76b14)


## 4. A floating point exception (divide-by-zero) issue was discovered in SoX in functon lsx_adpcm_encode() of adpcms.c file in line 97.
![image](https://github.com/dongyuma/sox-defects/assets/87286944/d32f3d3b-725a-49d5-9433-a616879fb0b0)
![image](https://github.com/dongyuma/sox-defects/assets/87286944/fc5f3111-92bb-4106-bc3b-141ca6eb0e72)







