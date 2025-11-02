# Iterator - Патерн Проєктування

Патерн Iterator дозволяє послідовно обходити елементи колекції, не розкриваючи її внутрішньої структури.

## Ідея

Клієнту не потрібно знати:
- як саме зберігаються елементи,
- чи це масив, список або дерево.

Ітератор надає уніфікований спосіб доступу до елементів.

## Структура

| Елемент     | Опис |
|------------|------|
| Iterator   | Об'єкт, який знає поточний стан перебору |
| Колекція   | Дані, які обходяться |
| Клієнт     | Використовує ітератор для послідовного доступу |

## Код

```csharp
class Iterator {
    private string[] items;
    private int index = 0;

    public Iterator(string[] i) { items = i; }

    public string Next() => index < items.Length ? items[index++] : null;
}

class Program {
    static void Main() {
        var it = new Iterator(new[] { "A", "B", "C" });
        string item;
        while ((item = it.Next()) != null)
            Console.WriteLine(item);
    }
}

