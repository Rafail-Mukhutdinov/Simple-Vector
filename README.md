# SimpleVector
Контейнер, упрощённый аналог `std::vector`. Написана обёртка указателя для этого контейнера. Используется идиома `RAII`.

## Инициализация

 - `SimpleVector(size_t size, const Type& value)` - создаёт вектор из size элементов, инициализированных значением value
 - `SimpleVector(size_t size)` - создаёт вектор из size элементов, инициализированных значением по умолчанию
 - `SimpleVector<T>test {value1, value2.. , value-n}` -Создаёт вектор из std::initializer_list


## Доступ к элементам


- `At(index)` - возвращает значение элемента в позиции index, или выбрасывает исключение out_of_range 
- `operator[index]` - возвращает значение элемента в позиции index


## Итераторы 
Тип итератора - `LegacyRandomAccessIterator `
 
Инвалидация итератора - любые операции с изменением размера, вставка в произвольную позицию (если без изменения capacity то инвалидируется end())
 - `begin()` - возвращает итератор на первый элемент массива
 - `end()` - возвращает итератор на позицию, за последним элементом массива

 
## Емкость

- `IsEmpty()` : возвращает true если вектор пуст
- `GetSize()`: возвращает количество элементов 
- `GetCapacity()`: возвращает количество элементов, которые могут храниться в выделенноой на данный момент памяти


## Модификаторы
 
- `PushBack( T value)` - вставка  элемента в конец массива
-` Insert(Iterator position, T value)` - вставка элемента в произвольную позицию
- `Resize(t_size value)` - изменение размера
- `PopBack()` - удаляет последний элемент массива
- `Erase(Iterator position)` - удаляет элемент в позиции position
- `swap(SimpleVector& other)` - обмен с `SimpleVector& other` данными `A <-> B`


## Сложность (эффективность) общих операций над вектором: 
 
- Произвольный доступ - константа `O(1)`
- Вставка или удаление элементов в конце - амортизируемая константа `O(1)`
- Вставка или удаление элементов - линейно по расстоянию до конца вектора `O(n)`
 
 ## Как использовать?
 - Поместите в папку вашего проекта файлы `array_ptr.h, simple_vector.h` из репозитория
 - Подключите в ваш файл SimpleVector  через директиву `#include "simple_vector.h"`
 - Пользуйтесь :)))
