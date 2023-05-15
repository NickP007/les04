# Створення додатку в ArgoCD

Створюємо додаток в ArgoCD який буде відслідковувати Git репозиторій продукту https://github.com/NickP007/go-demo-app та налаштовуємо автоматичну синхронізацію

Попередньо встановимо ArgoCD CLI інтерфейс:

## Інсталяція

1.1 Скачаємо та встановимо останню версію клієнта:

   ```bash
   curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64
   sudo install -m 555 argocd-linux-amd64 /usr/local/bin/argocd
   rm argocd-linux-amd64
   ```

1.2 Отримаємо тимчасовий пароль адмінстратора

   ```bash
   argocd admin initial-password -n argocd
   ```

1.3 За допомогою облікового запису `admin` та парлолю, отриманого в п.1.2 виконаємо автентифікацію на сервері ArgoCD

   ```bash
   argocd login 127.0.0.1:8080
   ```

1.4 Змінимо пароль за допомогою команди:

   ```bash
   argocd account update-password
   ```

## Налаштування

1. Заходимо в 'http://github.com' під своїм обліковим записом.

2. Робимо Fork репозиторію 'https://github.com/den-vasyliev/go-demo-app'

3. В браузері відкриваємо граіфчний інтерфейс додатку ArgoCD 'argocd.ubuntu.vm:8080', використовуємо обліковий запис 'admin' та встановлений пароль(див. п1.4).

4. Проводимо налаштування застосунку згідно з Відео 4.1

![Відео 4.1. Налаштування застосунку 'demo' в AgroCD](argo03.gif)
