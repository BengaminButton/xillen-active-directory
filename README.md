# XILLEN Active Directory Pentest Tool

## Описание
Мощный PowerShell инструмент для комплексного тестирования безопасности Active Directory. Инструмент автоматизирует процесс аудита AD, выявляя уязвимости, неправильные настройки и потенциальные векторы атак.

## Возможности
- **Domain Enumeration**: Полная информация о домене и его структуре
- **User Analysis**: Детальный анализ пользователей и их атрибутов
- **Group Enumeration**: Анализ групп и их членов
- **Computer Discovery**: Обнаружение и анализ компьютеров в домене
- **GPO Analysis**: Анализ групповых политик
- **Trust Relationships**: Анализ доверительных отношений
- **Privileged Account Discovery**: Поиск привилегированных аккаунтов
- **Service Account Analysis**: Анализ сервисных аккаунтов
- **SPN Enumeration**: Поиск пользователей с Service Principal Names
- **Delegation Analysis**: Анализ делегирования аутентификации
- **Password Policy Analysis**: Анализ политик паролей
- **Security Misconfigurations**: Выявление неправильных настроек безопасности

## Требования
- Windows PowerShell 5.1 или PowerShell Core 6.0+
- Active Directory PowerShell модуль
- Доступ к домену Active Directory
- Привилегии для чтения AD объектов

## Установка
```powershell
# Клонируйте репозиторий
git clone https://github.com/BengaminButton/xillen-active-directory
cd xillen-active-directory

# Убедитесь, что установлен AD модуль
Import-Module ActiveDirectory
```

## Использование
```powershell
# Базовое использование
.\AD_Pentest.ps1 -Domain "contoso.local" -Username "admin" -Password "P@ssw0rd"

# С указанием выходного файла
.\AD_Pentest.ps1 -Domain "contoso.local" -Username "admin" -Password "P@ssw0rd" -OutputFile "results.txt"
```

## Параметры
- `-Domain`: DNS имя домена для тестирования
- `-Username`: Имя пользователя для подключения к AD
- `-Password`: Пароль пользователя
- `-OutputFile`: Имя файла для сохранения результатов (по умолчанию: ad_pentest_results.txt)

## Функции

### Основные функции
- `Test-ADConnection()`: Проверка подключения к Active Directory
- `Get-ADDomainInfo()`: Получение информации о домене
- `Get-ADUsers()`: Перечисление всех пользователей
- `Get-ADGroups()`: Перечисление всех групп
- `Get-ADComputers()`: Перечисление всех компьютеров

### Анализ безопасности
- `Find-PrivilegedAccounts()`: Поиск привилегированных аккаунтов
- `Find-ServiceAccounts()`: Поиск сервисных аккаунтов
- `Find-UsersWithSPN()`: Поиск пользователей с SPN
- `Find-UsersWithDelegation()`: Поиск пользователей с делегированием
- `Find-UsersWithPreAuthNotRequired()`: Поиск пользователей без предварительной аутентификации
- `Find-UsersWithPasswordNeverExpires()`: Поиск пользователей с бессрочными паролями
- `Find-UsersWithReversibleEncryption()`: Поиск пользователей с обратимым шифрованием

### Политики безопасности
- `Get-ADPasswordPolicy()`: Анализ политики паролей
- `Get-ADAccountLockoutPolicy()`: Анализ политики блокировки аккаунтов

### Экспорт результатов
- `Export-Results()`: Сохранение результатов в файл
- `Show-Summary()`: Отображение сводки тестирования

## Примеры вывода
```
=== XILLEN Active Directory Pentest Summary ===
Domain: contoso.local
Username: admin
Output File: ad_pentest_results.txt
===============================================

[+] Active Directory connection successful!

[+] Starting Active Directory penetration testing...
[+] Results exported to: ad_pentest_results.txt
[+] JSON results exported to: ad_pentest_results.json

[+] Active Directory penetration testing completed!
[+] Check the output files for detailed results.
```

## Выходные файлы
- **ad_pentest_results.txt**: Основной отчет в текстовом формате
- **ad_pentest_results.json**: Детальные результаты в JSON формате

## Обнаруживаемые уязвимости
1. **Privileged Account Exposure**: Привилегированные аккаунты в группах
2. **Service Account Misuse**: Неправильное использование сервисных аккаунтов
3. **Delegation Vulnerabilities**: Уязвимости делегирования аутентификации
4. **Weak Password Policies**: Слабые политики паролей
5. **Account Lockout Issues**: Проблемы с блокировкой аккаунтов
6. **Trust Relationship Risks**: Риски доверительных отношений
7. **GPO Security Issues**: Проблемы безопасности групповых политик

## Безопасность
⚠️ **ВНИМАНИЕ**: Используйте только для тестирования собственных систем или с явного разрешения владельцев. Несанкционированное тестирование Active Directory может быть незаконным.

## Авторы
- **@Bengamin_Button** - Основной разработчик
- **@XillenAdapter** - Технический консультант

## Ссылки
- 🌐 **Website**: https://benjaminbutton.ru/
- 🔗 **Organization**: https://xillenkillers.ru/
- 📱 **Telegram**: t.me/XillenAdapter

## Лицензия
MIT License - свободное использование и модификация

## Поддержка
Для вопросов и предложений обращайтесь через Telegram или создавайте Issues на GitHub.

---
*XILLEN Active Directory Pentest Tool - профессиональный инструмент для тестирования безопасности корпоративных инфраструктур*
