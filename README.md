# Assigment3-DB

## Завдання 1:
### Транзакція1: читає стан рядку, де id=2
<img width="499" alt="Знімок екрана 2025-06-10 о 16 37 40" src="https://github.com/user-attachments/assets/59840d77-912f-4184-b0c3-1075481e25f6" />

### Транзакція2: робить незакомічені зміни в рядок, де id=2
<img width="632" alt="Знімок екрана 2025-06-10 о 16 38 20" src="https://github.com/user-attachments/assets/1514a078-1ee8-4d47-842d-f215259f5a9e" />

### Транзакція1: читає незакомічені зміни в рядку, де id=2
<img width="509" alt="Знімок екрана 2025-06-10 о 16 38 42" src="https://github.com/user-attachments/assets/9317700a-3550-48bf-942a-422b8e91f8ef" />


Транзакція1
<img width="809" alt="Знімок екрана 2025-06-10 о 16 34 37" src="https://github.com/user-attachments/assets/a578e02f-9b90-4f50-bef0-87c39997a564" />

Транзакція2
<img width="820" alt="Знімок екрана 2025-06-10 о 16 35 50" src="https://github.com/user-attachments/assets/2493d8b6-96f9-43a6-a660-5adbeb06a66e" />


## Завдання 2:
### Транзакція1: зчитує рядок в оригіналі
<img width="452" alt="Знімок екрана 2025-06-10 о 16 48 00" src="https://github.com/user-attachments/assets/11f8a288-ceb8-43ea-9b41-a504a1419910" />

### Транзакція2: робить зміни в цьому рядку, але не комітить

### Транзакція1: зчитує рядок, який було змінено, але не закомічено 
<img width="452" alt="Знімок екрана 2025-06-10 о 16 48 32" src="https://github.com/user-attachments/assets/cdf36a52-a252-4038-8a66-3f9681f3489c" />

### Транзакція2: комітить зміни

### Транзакція1: зчитує закомічені зміни
<img width="463" alt="Знімок екрана 2025-06-10 о 16 49 01" src="https://github.com/user-attachments/assets/2f7d9b5c-9c4c-4adf-bf5b-1d14c2f1f8b9" />

Транзакція1:

<img width="1004" alt="Знімок екрана 2025-06-10 о 16 51 04" src="https://github.com/user-attachments/assets/ff1a32a6-4392-4c7d-b702-8ef229792371" />

Транзакція2:

<img width="737" alt="Знімок екрана 2025-06-10 о 16 52 14" src="https://github.com/user-attachments/assets/31aa334e-4981-485e-9050-cbed7a312748" />

### Завдання 3:
У першому завданні ми можемо спостерігати проблему під назвою DIRTY READ,
коли одна транзакція бачить незакомічені зміни іншої транзакції. Така проблема виникає 
на рівні ізоляції READ UNCOMMITED.

У другому завданні, я показала проблему під назвою NON-REPETABLE READ,
коли транзакції можуть бачити закомічені зміни одна одної. Така проблема виникає на рівні ізоляції 
READ COMMITED.



