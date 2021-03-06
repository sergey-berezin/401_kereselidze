Задание 1 

Необходимо обнаружить все известные объекты на изображениях, находящихся в некоторой директории на диске.  

Критерий выполнения: Консольное приложение .NET (Framework или Core) обрабатывает указанную пользователем директорию выдаёт на экран информацию о найденных на изображениях объектах. 

Вариант 1: Программа печатает список найденных на изображении объектов по мере обработки каждого объекта. 
 

Требования к реализации: 

a. Компонент для распознавания должен принимать в качестве входных данных полный путь к директории, в качестве выходных данных выдавать информацию о классах объектов и ограничивающих прямоугольниках для каждого файла с изображением. 

b. Компонент размещен в отдельной библиотеке классов и должен быть переиспользован в других заданиях. 

c. Для распознавания изображений применяются заранее обученные модели из репозитория https://github.com/onnx/models. Пример исходного кода для работы с моделью YOLOv4: https://github.com/BobLd/YOLOv4MLNet. 

d. Распознавание выполняется асинхронно и результаты генерируются по мере обработки данных в директории. 

e. Распознавание нескольких файлов запускается одновременно с целью максимального использования всех ядер всех процессоров в системе. 

f. Компонент позволяет прекратить процесс распознавания и остановить все запущенные потоки. 

g. Для реализации многопоточности и асинхронности применяются: 

Вариант "b" - средства TPL Flow 


Задание 2
Необходимо предоставить пользователю приложение с графическим пользовательским интерфейсом для обнаружения известных объектов на изображениях в заданном каталоге и просмотра результатов. 
 
Критерий выполнения: разработано приложение WPF/WinForms/Avalonia (по выбору студента) позволяющее пользователю: 
1. Выбрать в графическом интерфейсе каталог, содержащий изображения и начать классификацию  
2. Просматривать информацию про обнаруженные объект. Информация должна динамически обновляться после обнаружения каждого нового объекта. 
3. Прерывать процесс распознавания изображений нажатием на кнопку 
4. Выбирать тип объекта и просматривать все изображения с заданным типом. 

Требования к реализации: 

Обработка изображений выполняется  c применением библиотеки классов, разработанной при выполнении Задачи 1. Задача 1 должна остаться работоспособной! 

Обработка изображений должна выполняться параллельно с работой пользовательского интерфейса. Пользовательский интерфейс не должен "зависать" пока идёт анализ изображений. 

Вариант "б": пользователю доступны для выбора все распознанные типы. При выборе определенного типа в окне приложения отображаются все изображения объектов этого типа.  Список изображений пополняется по мере распознавания файлов. 

 