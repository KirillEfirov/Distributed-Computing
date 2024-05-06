# Что такое распределенная система?

Распределенная система — это набор компьютерных программ, использующих вычислительные ресурсы нескольких отдельных вычислительных узлов для достижения одной общей цели. Ее также называют распределенными вычислениями или распределенной базой данных. Распределенная система основывается на отдельных узлах, которые обмениваются данными и выполняют синхронизацию в общей сети. Обычно узлы представляют собой отдельные физические аппаратные устройства, но это могут быть и отдельные программные процессы или другие рекурсивные инкапсулированные системы. Распределенные системы направлены на устранение узких мест или единых точек отказа в системе.

Распределенные вычислительные системы обладают следующими характеристиками:

1. Совместное использование ресурсов: в распределенной системе могут совместно использоваться оборудование, программное обеспечение или данные.
2. Параллельная обработка: одну и ту же функцию могут одновременно обрабатывать несколько машин.
3. Масштабируемость: вычислительная мощность и производительность могут масштабироваться по мере необходимости при добавлении дополнительных машин.
4. Обнаружение ошибок: упрощается обнаружение отказов.
5. Прозрачность: узел может обращаться к другим узлам в системе и обмениваться с ними данными.

# В чем разница между централизованной и распределенной системами?

<p align='center'>
  <img src=./images/centralized%20vs%20distributed.png>
</p>

В централизованной вычислительной системе все вычисления выполняются на одном компьютере и в одном месте. Основное различие между централизованными и распределенными системами заключается в модели взаимодействия между узлами системы. Состояние централизованной системы хранится в центральном узле, к которому индивидуально обращаются клиенты. Поскольку все узлы централизованной системы обращаются к центральному узлу, это может привести к перегрузке сети и замедлить ее работу. Централизованная система имеет единую точку отказа, тогда как в распределенной системе такой точки нет.

# Отличаются ли распределенные системы от микросервисов?

Микросервисная архитектура — это лишь один из типов распределенных систем. В ней приложение разбивается на отдельные компоненты, или «сервисы». К примеру, микросервисная архитектура может иметь сервисы, соответствующие бизнес-функциям (платежи, пользователи, продукты и др.), и каждый компонент будет обрабатывать бизнес-логику в своей сфере ответственности. В этом случае в системе будет несколько резервных копий сервисов, и у сервисов не будет единой точки отказа.

# Преимущества, недостатки и риски распределенных систем

Распределенные системы часто помогают повысить надежность и производительность системы. Надежность повышается за счет устранения единых точек отказа и узких мест. Узлы распределенной системы обеспечивают избыточность, поэтому при отказе любого узла его могут заменить другие. Производительность повышается благодаря тому, что узлы можно легко масштабировать по горизонтали и вертикали. В случае большой нагрузки на систему можно добавить дополнительные узлы, которые помогут с ней справиться. Для обработки большой нагрузки можно также повысить производительность отдельных узлов.

Однако обратной стороной этих преимуществ может стать разрастание системы, когда система становится слишком сложной и ее техническое обслуживание затрудняется. По мере усложнения системы у команды могут возникать трудности с эффективным управлением, организацией и совершенствованием системы. В частности, может возникнуть проблема с пониманием того, как связаны между собой различные компоненты и кто является владельцем конкретного программного компонента. Бывает трудно понять, как внести изменения в компоненты, чтобы максимально повысить работоспособность и при этом избежать негативного воздействия на зависимые компоненты и клиентов.

# Архитектура распределенных систем

## Клиент-сервер

В клиент-серверной архитектуре ответственность делится на две части. Клиент отвечает за представление (интерфейс пользователя) и поддерживает связь с сервером по сети. Сервер отвечает за обработку бизнес-логики и управление состоянием. Клиент-серверную архитектуру можно легко превратить в централизованную, если у сервера отсутствует избыточность. По-настоящему распределенная клиент-серверная модель должна иметь несколько серверных узлов для распределения клиентских подключений. Большинство современных клиент-серверных архитектур — это клиенты, которые подключаются к инкапсулированной распределенной системе на сервере.

## Многоуровневая

Многоуровневая архитектура является расширением клиент-серверной архитектуры. Сервер в многоуровневой архитектуре разбивается на более мелкие узлы, которые выполняют дополнительные обязанности внутреннего сервера, такие как обработка данных и управление данными. Эти дополнительные узлы используются для асинхронного выполнения длительных заданий, высвобождая остальные серверные узлы для обработки запросов клиентов и взаимодействия с хранилищем данных.

## Одноранговая

Каждый узел одноранговой распределенной системы содержит полный экземпляр приложения. Отсутствует разделение на узлы представления и узлы обработки данных. Узел содержит уровень представления и уровни обработки данных. Одноранговые узлы могут содержать полные данные о состоянии всей системы.

Преимуществом одноранговой системы является ее огромная избыточность. После инициализации и подключения однорангового узла к сети он находит другие одноранговые узлы, устанавливает с ними связь и синхронизирует свое локальное состояние с состоянием всей системы. Эта особенность означает, что отказ одного узла в одноранговой системе не нарушит работу других узлов. Одноранговая система продолжит работать.

# Сервис-ориентированная архитектура ([SOA](SOA.md))

Сервис-ориентированная архитектура (SOA) является предшественницей микросервисной. Основное различие между SOA и микросервисной архитектурой заключается в области действия узлов: область действия микросервисных узлов относится к уровню функций. В микросервисной архитектуре узел инкапсулирует бизнес-логику для выполнения определенного набора функций, например обработки платежей. Микросервисная архитектура имеет несколько различных узлов бизнес-логики, которые взаимодействуют с независимыми узлами баз данных. Для сравнения, узлы SOA инкапсулируют целое приложение или подразделение компании. Границы сервиса для узлов SOA обычно охватывают всю систему баз данных в узле.

Микросервисная архитектура стала более популярной альтернативой SOA благодаря своим преимуществам. Микросервисы проще компоновать, поэтому команды могут многократно использовать функциональные возможности, предоставляемые небольшими сервисными узлами. Микросервисная архитектура более устойчива и допускает динамическое вертикальное и горизонтальное масштабирование.

# Примеры использования распределенных систем

Сегодня распределенные системы используются многими приложениями. Мобильные и веб-приложения с интенсивным трафиком являются распределенными системами. Пользователи подключаются по принципу «клиент-сервер», где клиентом является веб-браузер или мобильное приложение. В этом случае сервер представляет собой распределенную систему. Современные веб-серверы следуют модели многоуровневой системы. Для делегирования запросов множеству серверных логических узлов, которые взаимодействуют через системы очередей сообщений, используется балансировщик нагрузки.

Популярным инструментом для работы с распределенными системами является платформа Kubernetes, которая позволяет создать распределенную систему из набора контейнеров. Контейнеры образуют узлы распределенной системы, а Kubernetes оркеструет сетевое взаимодействие между узлами и выполняет динамическое горизонтальное и вертикальное масштабирование узлов в системе.

Другой хороший пример распределенных систем — криптовалюты, такие как биткоин или эфириум, которые являются одноранговыми распределенными системами. Каждый узел в криптовалютной сети представляет собой полную копию всей истории реестра валюты. Когда валютный узел подключают к сети, он выполняет начальную загрузку. Для этого он устанавливает связь с другими узлами и загружает полную копию реестра. Кроме того, у криптовалют есть клиенты, или «кошельки», которые подключаются к узлам реестра через протокол JSON RPC.