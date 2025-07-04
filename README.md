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

Продемонстрована аномалія називається DIRTY READ, адже одна з транзакцій може читати незакомічені зміни іншої.
Така проблема виникає на рівні ізоляції READ UNCOMMITED.

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

NON-REPEATABLE READ це аномалія читання, коли одна з транзакцій зчитує рядок, потім інша транзакція
змінює його і комітить ці зміни та при повторному читанні першої транзакції зміненого рядку дані вже будуть інші.
Адже така аномалія відбувається на рівні ізоляції READ COMMITED і нижче.

### Завдання 3:
У першому завданні ми можемо спостерігати проблему під назвою DIRTY READ,
коли одна транзакція бачить незакомічені зміни іншої транзакції. Така проблема виникає 
на рівні ізоляції READ UNCOMMITED.

У другому завданні, я показала проблему під назвою NON-REPETABLE READ,
коли транзакції можуть бачити закомічені зміни одна одної. Така проблема виникає на рівні ізоляції 
READ COMMITED.

## Бонусне1

Запустила першу транзакцію1, що прочитала рядок, де id=1.
<img width="564" alt="Знімок екрана 2025-06-10 о 19 47 19" src="https://github.com/user-attachments/assets/d9c1cb2f-3353-45da-a204-2d57492b94cf" />

Запустила іншу транзакцію2, що змінює це рядок
<img width="1179" alt="Знімок екрана 2025-06-10 о 19 47 59" src="https://github.com/user-attachments/assets/8ebac94c-8b65-43f7-a733-8edecb9e4dde" />

Транзакцію2 не вдалось виконати, адже встановлений рівень ізоляції REPEATABLE READ, і наступна транзакція2 не може бути виконана, доки не завершиться попередня транзакція1.

<img width="572" alt="Знімок екрана 2025-06-10 о 19 50 11" src="https://github.com/user-attachments/assets/687e10ce-0984-4dbf-9aea-6c693c2a30f4" />
Я завершила транзакцію1 закомітивши, і тепер транзакція2 успішно виконалась

<img width="549" alt="Знімок екрана 2025-06-10 о 19 54 22" src="https://github.com/user-attachments/assets/5230284d-9f2b-4cae-8078-9e911b45499a" />

## Бонусне2
Різниця між схожими сценаріями READ COMMITED та REPEATABLE READ:
в READ COMMITED зміни були прочитані та не співпадали, а в REPEATABLE READ  транзакція на зміну рядка не могла бути виконана, доки не завершиься транзакція читання, отже обидва SELECT в транзакції читання повернули однаковий результат.

## Бонусне3
### Сценарій:
Транзакція1: змінює рядок, де id =4

<img width="630" alt="Знімок екрана 2025-06-10 о 20 08 20" src="https://github.com/user-attachments/assets/88ed1c22-f05c-4656-bb4a-a17ebbd6ce77" />


Транзакція2: змінює рядок, де id=5

<img width="600" alt="Знімок екрана 2025-06-10 о 20 08 47" src="https://github.com/user-attachments/assets/549e8977-9158-47c1-9a1f-3b9088ac257c" />


Транзакція1: змінює рядок, де id=5

<img width="1142" alt="Знімок екрана 2025-06-10 о 20 09 20" src="https://github.com/user-attachments/assets/0902952c-df1e-41c1-83b4-39145140da68" />
Де транзакція застрягла, та чекає, доки попередня транзакція, що заблокувала рядок з id=5 завершить своє виконання

Транзакція2: змінює рядок, де id=4

<img width="584" alt="Знімок екрана 2025-06-10 о 20 10 26" src="https://github.com/user-attachments/assets/780bd339-a21c-4f4a-a24a-40134a1b17c5" />

Отримали помилку Deadblock

Помилка Deadblock була викликана, адже транзакція1 при зміні рядку з id=4 заблокувала його і не завершилась, далі транзакція2 при зміні рядку з id=5 заблокувала його і не завершилась. Далі транзакція1 намагалась змінити рядок з id=5, але їй потрібно зачекати, доки попередня транзакція завершиться розблокує цей рядок. Отже транзакції стали взаємно залежними в очікуванні завершення одна одної


