result = []

def divider(a, b):
    try:
        if a < b:
            raise ValueError("a менше, ніж b")
        if b > 100:
            raise IndexError("b більше 100")
        return a / b
    except Exception as e:
        print(f"Помилка у функції divider: {type(e).__name__} - {e}")
        return None


data = {10: 2, 2: 5, "123": 4, 18: 0, []: 15, 8: 4}

for key in data:
    try:
        res = divider(key, data[key])
        result.append(res)
    except TypeError as e:
        print(f"TypeError: неможливо виконати операцію для ключа {key} ({e})")
    except ZeroDivisionError:
        print(f"ZeroDivisionError: ділення на нуль для ключа {key}")
    except Exception as e:
        print(f"Інша помилка: {type(e).__name__} - {e}")

print("Результат:", result)
