### CloudFrame
Основополагающий каркас для создания и управления инфраструктурой с модульными конфигурациями.

#### Генерация ключа сервисного аккаунта
1. Войдите в Yandex.Cloud CLI:
   ```bash
   yc init
   ```
2. Создайте сервисный аккаунт:
   ```bash
   yc iam service-account create --name terraform-bot --folder-id <folder-id>
   ```
3. Назначьте роли:
   ```bash
   yc resource-manager folder add-access-binding --id <folder-id> --role editor --service-account-id <service-account-id>
   yc resource-manager folder add-access-binding --id <folder-id> --role vpc.admin --service-account-id <service-account-id>
   ```
4. Сгенерируйте ключ и сохраните в `services/stage.tfvars.json`:
   ```bash
   yc iam key create --service-account-id <service-account-id> --output services/stage.tfvars.json
   ```

---
Документация будет дополняться по ходу развития проекта.
