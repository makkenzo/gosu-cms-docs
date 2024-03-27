## 1 этап:

### Получение данных о товаре

> product model

```ts
interface IProduct {
    id: string; // Уникальный идентификатор продукта

    fatAmount: number;
    proteinsAmount: number;
    carbohydratesAmount: number;
    energyAmount: number;
    fatFullAmount: number;
    proteinsFullAmount: number;
    carbohydratesFullAmount: number;
    energyFullAmount: number;
    weight: number;

    order: number; // поле для сортировки продукта

    title: string; // Название продукта
    description: string; // Описание продукта
    tags: string[];
    images: string[]; // Ссылки на изображения продукта
    price: number; // Цена продукта

    sizePrices: [
        {
            id: string;
            productId: string;
            name: string;
            price: number;
            discount: number;
        }
    ];

    seoDescription: string;
    seoText: string;
    seoKeywords: string;
    seoTitle: string;

    categoryId: string; // Категория; к которой относится продукт
    groupId: string; // Группа; к которой относится продукт
    parentGroup: number; // External menu group

    articul: string;
    brand: string;
    color: string;
    season: string;
    sex: 'Male' | 'Female' | 'All';

    quantityRemaining: number; // Количество доступных единиц продукта

    additionalInfo: string; // Дополнительная информация для особых случаев (ИКПУ или что-то ещё)

    createdAt: string; // Дата добавления продукта в каталог
    updatedAt: string; // Дата последнего обновления информации о продукте

    isDeleted: boolean;
}
```

> category model

```ts
interface ICategory {
    id: string; // Уникальный идентификатор категории

    title: string; // Название категории
    description?: string; // Описание категории, необязательное поле
    parentId?: string; // Идентификатор родительской категории для создания иерархии

    imageUrl?: string; // Ссылка на изображение, представляющее категорию

    seoTitle?: string; // SEO заголовок для категории
    seoDescription?: string; // SEO описание для категории
    seoKeywords?: string; // SEO ключевые слова для категории

    order?: number; // Поле для сортировки категории среди других категорий

    createdAt?: string; // Дата создания категории
    updatedAt?: string; // Дата последнего обновления категории

    isVisible?: boolean; // Флаг, указывающий, должна ли категория отображаться пользователям
}
```

> group model

```ts
interface IGroup {
    id: string; // Уникальный идентификатор группы

    title: string; // Название группы
    description?: string; // Описание группы, необязательное поле

    imageUrl?: string; // Ссылка на изображение, представляющее группу

    seoTitle?: string; // SEO заголовок для группы
    seoDescription?: string; // SEO описание для группы
    seoKeywords?: string; // SEO ключевые слова для группы
    products?: string[]; // Список идентификаторов продуктов, входящих в группу

    order?: number; // Поле для сортировки группы среди других групп

    createdAt?: string; // Дата создания группы
    updatedAt?: string; // Дата последнего обновления группы

    isVisible?: boolean; // Флаг, указывающий, должна ли группа отображаться пользователям
}
```

Авторизация

> user model

```ts
interface IUser {
    id: string; // Уникальный идентификатор пользователя
    externalId?: string; // Уникальный идентификатор пользователя для интеграции внешних систем

    name: string; // Полное имя пользователя для обращения и доставки

    surname?: string;
    middleName?: string;

    address?: string; // Адрес доставки

    comment: string; // Коментарий пользователю
    tags: string[]; // Теги для работы менеджеров
    categoriesIds: string[]; // Список Id групп пользователей

    phone: string; // Phone пользователя для входа и уведомлений
    email: string; // Email пользователя для входа и уведомлений
    password: string; // Хэш пароля для безопасности

    cultureName: string; // Короткое имя культуры для работы менеджера

    birthday?: string; // Дата рождения

    sex: 'Male' | 'Female' | 'Other'; // пол пользователя

    cards: [
        {
            id: string;
            track: string;
            number: string;
            validToDate: string;
        }
    ]; // Сохранённые спосабы оплаты

    walletBalances: [
        {
            id: string;
            name: string;
            type: 0;
            balance: 0;
        }
    ]; // Сохранённые карты пользователя для внутренних бонусов

    isDeleted: boolean;
}
```

Функции работы с товарами (желаемое, корзина)

```ts
...
```

## 2 этап: Админ-панель:

Администрирование товаров

```ts
...
```

Администрирование заказов

```ts
...
```

Интеграция с 1С

```ts
...
```
