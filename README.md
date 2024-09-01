# Verdapi

Verdapi, Node.js, Angular ve Laravel için basit ve kullanıcı dostu bir API kütüphanesidir. Bu kütüphane, geliştiricilere çeşitli platformlar arasında hızlı ve kolay bir şekilde API oluşturma ve kullanma imkanı sağlar.

## Özellikler

- **Modüler Yapı:** API işlevselliğini modüller halinde organize edebilme.
- **Çapraz Platform Desteği:** Node.js, Angular ve Laravel için destek.
- **Kolay Entegrasyon:** Basit ve temiz bir API tasarımıyla kolayca entegre edilebilir.
- **Genişletilebilirlik:** İhtiyaçlarınıza göre genişletilebilir yapı.

## Kurulum

### Node.js

1. Proje dizinine gidin:
   ```bash
   cd your-nodejs-project
   ```

2. Verdapi'yi yükleyin:
   ```bash
   npm install verdapi
   ```

### Angular

1. Proje dizinine gidin:
   ```bash
   cd your-angular-project
   ```

2. Verdapi'yi yükleyin:
   ```bash
   npm install verdapi
   ```

### Laravel

1. Proje dizinine gidin:
   ```bash
   cd your-laravel-project
   ```

2. Composer kullanarak Verdapi'yi yükleyin:
   ```bash
   composer require verdapi
   ```

## Kullanım

### Node.js

```javascript
const { APIClient } = require('verdapi');

const apiClient = new APIClient('https://api.example.com');

// Bir kullanıcıyı getirme
apiClient.get('/users/1').then(user => console.log(user));

// Yeni bir kullanıcı oluşturma
apiClient.post('/users', { name: 'John Doe', email: 'john@example.com' })
    .then(user => console.log(user));
```

### Angular

```typescript
import { Component, OnInit } from '@angular/core';
import { UserService } from 'verdapi';

@Component({
  selector: 'app-user',
  template: '<p>{{ user.name }}</p>'
})
export class UserComponent implements OnInit {
  user: any;

  constructor(private userService: UserService) {}

  ngOnInit() {
    this.userService.getUser(1).subscribe(user => this.user = user);
  }
}
```

### Laravel

```php
use Verdapi\UserService;

$userService = new UserService();

// Bir kullanıcıyı getirme
$user = $userService->getUser(1);
echo $user->name;

// Yeni bir kullanıcı oluşturma
$newUser = $userService->createUser([
    'name' => 'John Doe',
    'email' => 'john@example.com'
]);
echo $newUser->id;
```

## Katkıda Bulunma

Katkılarınızı memnuniyetle karşılıyoruz! Eğer bu projeye katkıda bulunmak istiyorsanız, lütfen şu adımları izleyin:

1. Bu repository'yi forklayın.
2. Yeni bir özellik dalı (`feature/new-feature`) oluşturun.
3. Değişikliklerinizi commitleyin (`git commit -am 'Add new feature'`).
4. Dalınıza push edin (`git push origin feature/new-feature`).
5. Bir Pull Request açın.

## Lisans

Bu proje [MIT Lisansı](LICENSE) altında lisanslanmıştır.
