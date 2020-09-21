```php
try {
    $user = selector::get('object')->id(Service::Auth()->getUserId());
    $userGroups = $user->getValue('groups');
    /**
     * Скидки по группам пользователей
     * @var iUmiObject $item
     */
    foreach ($this->module->getAllDiscounts('order', true) as $item) {
        $orderDiscount = discount::get($item->getId());
        foreach ($orderDiscount->getDiscountRules() as $rule) {
            if ($rule->getName() != 'userGroups' || !array_intersect($rule->getValue('user_groups'), $userGroups)) {
                continue;
            }
            $proc = $orderDiscount->getDiscountModificator()->getValue('proc');
            if ($proc > $discount) {
                $discount = $proc;
            }
        }
    }
} catch (Throwable $e) {
}
```
