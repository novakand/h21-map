# Angular Модуль Maps


### `Компоненты:`

#### `h21-map:`

##### `Подключение и использование:`
```javascript

<h21-map 
[latitude]="27.215556209029693" 
[longitude]="18.45703125" 
[zoom]="3" 
(mapReady)="mapReady($event)" 
(mapClick)="mapClick($event)"
(mapMouseMove)="mapMouseMove($event)">
</h21-map>

```

```javascript
import { H21MapComponent } from "../";

@ViewChild(H21MapComponent) public map: H21MapComponent;

```

### `Входящие параметры:`

| Inputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| latitude            | Широта, которая определяет центр карты. <br> Тип: number   <br> Значение по умолчанию: 0                                                                                                                             |
| longitude       | Долгота, которая определяет центр карты. <br> Тип: number   <br> Значение по умолчанию: 0    
| enableDraggable           | Включает / отключает, перетаскивание карты <br> Тип: boolean   <br> Значение по умолчанию: true   |
| maxZoom           | Максимально допустимый уровень масштабирования карты. Если не указано, никакие ограничения на уровень масштабирования не применяются. <br> Тип: number  <br> Значение по умолчанию: 22  |
| minZoom           | Минимальный допустимый уровень масштабирования карты. Если не указано, никакие ограничения на уровень масштабирования не применяются. <br> Тип: number   <br> Значение по умолчанию: 2   |
| zoom       |Уровень масштабирования карты. Уровень масштабирования по умолчанию - 3. <br> Тип: number   <br> Значение по умолчанию: 3 
| enableClick       |Включает/ отключает, отслеживание события клика по карте. <br> Тип: boolean   <br> Значение по умолчанию: true
| enableDoubleClickZoom       |Включает/ отключает, отслеживание события двойного клика по карте <br> Тип: boolean   <br> Значение по умолчанию: true
| enableDefaultControl       |Включает/ отключает, по умолчанию панели управления на карте ( По умолчанию только подключен контроль масштабирования) <br> Тип: boolean   <br> Значение по умолчанию: false
| enableScrollwheel       |Включает/ отключает, масштабирование с помощью колеса прокрутки на карте <br> Тип: boolean   <br> Значение по умолчанию: true
| enableTrafficLayer       |Включает/ отключает, отображение слой пробок на карте <br> Тип: boolean   <br> Значение по умолчанию: false
| enableTransitLayer       |Включает/ отключает, отображение слой транспорта на карте <br> Тип: boolean   <br> Значение по умолчанию: false
| defaultCursor       | Выбранный курсор на карте <br> Тип: `CursorType`   <br> Значение по умолчанию: `CursorType.default`
| provider       | Выбранный провайдер карт <br> Тип: `MapType`   <br> Значение по умолчанию: `MapType.google`

### `Исходящие параметры:`

| Outputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| boundsChange            | Это событие вызывается, когда границы области просмотра изменились. <br> Тип:  Subject `<IBounds>`   |                                                                                                                     
| zoomChange       | Это событие вызывается, когда масштаб карты измененился. <br> Тип: number     | 
| mapReady       | Это событие вызывается, когда карта загрузилась.   |
| mapClick       | Это событие вызывается, когда произошел клик по карте. <br> Тип: Subject `IPosition`    |
| mapDblClick       | Это событие вызывается, когда произошел двойной клик по карте. <br> Тип: Subject `MouseEvent`    |
| mapRightClick       | Это событие вызывается, когда произошел  клик правой клавишей мыши по карте. <br> Тип: Subject `MouseEvent`    |
| mapMouseOver       | Это событие вызывается, когда указатель мыши будет наведен на карту. <br> Тип: Subject `MouseEvent`    |
| mapMouseOut       | Это событие вызывается, когда указатель мыши будет выведен с карту. <br> Тип: Subject `MouseEvent`    |
| mapMouseDown       | Это событие вызывается, когда указатель мыши будет выведен с карту. <br> Тип: Subject `MouseEvent`    |
| mapMouseDown       | Это событие вызывается, когда кнопка мыши нажата. <br> Тип: Subject `MouseEvent`    |
| mapMouseUp       | Это событие вызывается, когда кнопка мыши отпущен. <br> Тип: Subject `MouseEvent`    |
| mapMouseMove       | Это событие вызывается, указатель мыши перемещается по карте. <br> Тип: Subject `MouseEvent`    |
| countLoadsMarkers       | Количество загруженных точек (маркеров на карте). <br> Тип: number   |
| responseMapError       | Ответ от карты (если в работе карты пришли ошибки). <br> Тип: string   |
| geolocationChange       | Это событие вызывается когда был осуществлен запрос на геопозиционирование  . <br> Тип: Subject `IPosition` |

### `Доступные методы:`

| Методы               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| getGeoLocation            | Получить координаты геопозиционирования <br> Тип:  Subject `<IPosition>`   |                                                                                                                     

#### `h21-map-info-box `

##### `Подключение и использование:`
```javascript

<h21-map-info-box  
[longitude]="27.2155562" 
[latitude]="18.45703125" 
[isOpen]="isOpen">
<div class="tooltip_content">
<div class="tooltip_label">
    {{text}}        
</div>
<div class="tooltip-value">
{{text}}
</div>
</div>
<div class="tooltip_content">
<div class="tooltip_label">
    {{text}}
</div>
<div class="tooltip-value">
   {{text}}
</div>
</div>
</h21-map-info-box>

```

```javascript
import { H21MapInfoBoxComponent } from "../";

@ViewChild(H21MapInfoBoxComponent) public box: H21MapInfoBoxComponent;

```
### `Входящие параметры:`

| Inputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| latitude            | Широта, для отображения информационного окна. <br> Тип: number   <br> Значение по умолчанию: 0                                                                                                                             |
| longitude       | Долгота,  для отображения информационного окна. <br> Тип: number   <br> Значение по умолчанию: 0    |
| isOpen       | Включает/ отключает отображение информационного окна. <br> Тип: boolen   <br> Значение по умолчанию: false    |
| zIndex       | Определяет положение элемента и нижестоящих элементов по оси z. <br> Тип: number   <br> Значение по умолчанию: 99    |
| closeBoxURL       | Установить  url  картинки закрытия информационного окна. <br> Тип: string   <br> Значение по умолчанию: ' '    |


### `Директивы:`
#### `h21-map-marker `

##### `Подключение и использование:`
```javascript

<h21-marker 
*ngFor="let m of markers; let i = index"
(markerClick)="clickedMarker(m, i)"
(markerMouseOut)="markerMouseOut(m)"
(markerMouseOver)="markerMouseOver(m)" 
[latitude]="m.lat"
[longitude]="m.lng">
</h21-marker>

```

```javascript
import { H21MapMarkerDirective } from "../";

@ViewChild(H21MapMarkerDirective) public marker: H21MapMarkerDirective;

```
### `Входящие параметры:`

| Inputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| latitude            | Широта положение маркера. <br> Тип: number   <br> Значение по умолчанию: 0                                                                                                                             |
| longitude       | Долгота,  положение маркера. <br> Тип: number   <br> Значение по умолчанию: 0    |
| title       | Название маркера <br> Тип: string   <br> Значение по умолчанию: ''    |
| zIndex       | Определяет положение элемента и нижестоящих элементов по оси z. <br> Тип: number   <br> Значение по умолчанию: 100    |
| opacity       | Прозрачность маркера. <br> Тип: number   <br> Значение по умолчанию: 1    |
| label       | Метка (один заглавный символ) для маркера. <br> Тип: string   <br> Значение по умолчанию: ''    |
| iconUrl       | Значок (URL изображения) для переднего плана. <br> Тип: string   <br> Значение по умолчанию: ''    |
| width       | Размер по ширине (URL изображения) для переднего плана. <br> Тип: number   <br> Значение по умолчанию: 22    |
| height       | Размер по высоте (URL изображения) для переднего плана. <br> Тип: number   <br> Значение по умолчанию: 22   |
| markerVisible       | Включает/ отключает, отображение маркера на карте. <br> Тип: boolean   <br> Значение по умолчанию: true   |
| fitBonds       | Отобразить маркер в области видимости карты. <br> Тип: boolean   <br> Значение по умолчанию: true   |
| markerDraggable       |  Включает/ отключает, перетаскивание маркера по карте. <br> Тип: boolean   <br> Значение по умолчанию: false   |
| markerClickable       |  Включает/ отключает, клика по маркеру. <br> Тип: boolean   <br> Значение по умолчанию: true   |
| markerCurcor       |  Установить курсор при наведении на маркер. <br> Тип: `CursorType`   <br> Значение по умолчанию: `CursorType.default`    |


### `Исходящие параметры:`

| Outputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| markerClick            | Событие вызывается, когда произошел клик по маркеру. <br> Тип: Subject `MouseEvent`  |                    
| markerDragEnd            | Событие вызывается, когда завершенно перетаскивание маркера. <br> Тип: Subject `MouseEvent`  |  
| markerMouseOver            | Событие вызывается, когда курсор мыши наведен на маркер. <br> Тип: Subject `MouseEvent`  |          
| markerMouseOut            | Событие вызывается, когда курсор мыши выведен с маркера. <br> Тип: Subject `MouseEvent`  |   

#### `h21-map-circle `

##### `Подключение и использование:`
```javascript

<h21-circle 
[latitude]="27.2155562" 
[longitude]="18.45703125" 
[radius]="5000"
[fillColor]="'#0044d6'"
[strokeColor]="'#0044d6'"
[circleDraggable]="true"
[circleEditable]="true">
</h21-circle>

```

```javascript
import { H21MapCircleDirective } from "../";

@ViewChild(H21MapCircleDirective) public circle: H21MapCircleDirective;

```
### `Входящие параметры:`

| Inputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| latitude            | Широта положение радиуса. <br> Тип: number   <br> Значение по умолчанию: 0                                                                                                                             |
| longitude       | Долгота,  положение радиуса. <br> Тип: number   <br> Значение по умолчанию: 0    |
| zIndex       | Определяет положение элемента по оси z. <br> Тип: number   <br> Значение по умолчанию: 100    |
| circleVisible       | Включает/ отключает, отображение радиуса на карте. <br> Тип: boolean   <br> Значение по умолчанию: true   |
| fitBonds       | Отобразить маркер в области видимости карты. <br> Тип: boolean   <br> Значение по умолчанию: true   |
| circleDraggable       |  Включает/ отключает, перетаскивание радиуса по карте. <br> Тип: boolean   <br> Значение по умолчанию: false   |
| circleClickable       |  Включает/ отключает, клика по радиусу. <br> Тип: boolean   <br> Значение по умолчанию: true   |
| circleEditable       |  Включает/ отключает, редактирование радиуса. <br> Тип: boolean   <br> Значение по умолчанию: false   |
| radius       |  Радиус в метрах на поверхности Земли. <br> Тип: number   <br> Значение по умолчанию: 0   |
| strokeColor       |  Цвет обводки. Поддерживаются все цвета CSS3, кроме расширенных именованных цветов. <br> Тип: string   <br> Значение по умолчанию: #0044d6   |
| strokeOpacity       |  Прозрачность обводки <br> Тип: number   <br> Значение по умолчанию: 0.7   |
| strokeWeight       |  Ширина обводки в пикселях <br> Тип: number   <br> Значение по умолчанию: 3.5   |
| fillColor       |  Цвет заливки. Поддерживаются все цвета CSS3, кроме расширенных именованных цветов. <br> Тип: string   <br> Значение по умолчанию: 0044d6  |
| fillOpacity       |  Прозрачность заливки.  <br> Тип: number   <br> Значение по умолчанию: 0.08  |


### `Исходящие параметры:`

| Outputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| circleClick            | Событие вызывается, когда произошел клик по маркеру. <br> Тип: Subject `MouseEvent`  |  
| circleDblClick            | Событие вызывается, когда произошел двойной клик по радиусу. <br> Тип: Subject `MouseEvent`  |                 
| circleDragEnd            | Событие вызывается, когда завершенно перетаскивание радиуса. <br> Тип: Subject `MouseEvent`  |   
| circleMouseDown            | Событие вызывается, когда нопка мыши нажата над радиусом. <br> Тип: Subject `MouseEvent`  |                              
| circleMouseMove            | Событие вызывается, когда  радиуса. <br> Тип: Subject `MouseEvent`  |    
| circleMouseOut            | Событие вызывается, когда курсор мыши выведен c радиуса. <br> Тип: Subject `MouseEvent`  |    
| circleMouseOver            | Событие вызывается,  когда указатель мыши будет наведен на радиус <br> Тип: Subject `MouseEvent`  | 
| circleMouseUp            | Событие вызывается,  когда отпущена любая из стандартных клавиш мыши радиуса. <br> Тип: Subject `MouseEvent`  |  
| circleRadiusChange            | Событие вызывается, когда изменился радиус. <br> Тип: Subject `MouseEvent`  |  
| circleCenterChange            | Событие вызывается, когда центр радиуса изменился. <br> Тип: Subject `MouseEvent`  |                                                                                                          

#### `h21-map-cluster `

##### `Подключение и использование:`
```javascript

<h21-map-cluster
[gridSize]="300" 
[iconUrl]="../images.png"
[maxZoom]="10">
</h21-map-cluster>
```

```javascript
import { H21MapClusterDirective } from "../";

@ViewChild(H21MapClusterDirective) public cluster: H21MapClusterDirective;
```

### `Входящие параметры:`

| Inputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| gridSize       |  Размер сетки. <br> Тип: number   <br> Значение по умолчанию: 200    |
| maxZoom       | Определяет максимальный уровень масштабирования для кластера . <br> Тип: number   <br> Значение по умолчанию: 100    |
| iconUrl       | Значок (URL изображения) для переднего плана. <br> Тип: string   <br> Значение по умолчанию: ''    |
| width       | Размер по ширине (URL изображения) для переднего плана. <br> Тип: number   <br> Значение по умолчанию: 54    |
| height       | Размер по высоте (URL изображения) для переднего плана. <br> Тип: number   <br> Значение по умолчанию: 54   |


### `Исходящие параметры:`

| Outputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| clusterClick  | Событие вызывается, когда произошел клик по кластеру. <br> Тип: Subject `MouseEvent`  |  

#### `h21-map-geocoding `

##### `Подключение и использование:`
```javascript

<h21-map-geocoding></h21-map-geocoding>
```

```javascript
import { H21MaGeocodingDirective } from "../";

@ViewChild(H21MaGeocodingDirective) public cluster: H21MaGeocodingDirective;
```
### `Входящие параметры:`

| Inputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| latitude       |  Широта, для получения адреса по координатам. <br> Тип: number   <br> Значение по умолчанию: 200    |
| longitude       | Долгота, для получения адреса по координатам . <br> Тип: number   <br> Значение по умолчанию: 100    |
| address       | Текст (название города, улицы) <br> Тип: string   <br> Значение по умолчанию: ''    |


### `Исходящие параметры:`

| Outputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| directGeocodingResponse  |Ответ от прямого геокодирования,  используется для определения координат по названию объекта или его адресу <br> Тип:Subject `IPosition`  |  
| reverseGeocodingResponse  |Ответ от обратного геокодирования,используется для определения адреса объекта по его координатам <br> Тип:Subject `IPoint`  |  

### `Доступные методы:`

| Методы               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| getCoordinates(address)  |Ответ от прямого геокодирования,  используется для определения координат по названию объекта или его адресу <br> Тип:Observable `IPosition`|
| getAddress(latitude, longitude)  |Ответ от обратного геокодирования,используется для определения адреса объекта по его координатам <br> Тип:Observable `IPoint`  |  

#### `h21-map-search `

##### `Подключение и использование:`
```javascript

<h21-map-search 
[query]="query" 
(searchResponce)="responceSearch($event)"
 #search>
 </h21-map-search>
```

```javascript
import { H21MaSearchDirective } from "../";

@ViewChild(H21MaSearchDirective) public search: H21MaSearchDirective;
```

### `Входящие параметры:`

| Inputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| query       | Текст поиска по карте (по названию улицы или названию объекта) <br> Тип: string   <br> Значение по умолчанию: ''    |
| language       | Запрос отправлять для опредделенного языка (формат...) <br> Тип: number   <br> Значение по умолчанию: 100    |
| countPlace       |Количество возвращаемых результатов <br> Тип: number   <br> Значение по умолчанию: 10    |


### `Исходящие параметры:`

| Outputs               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| searchResponce  | Результаты поиска по карте <br> Тип:Subject `IPoint`  |  


### `Доступные методы:`

| Методы               | Описание                                                                                                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| searcPlace(text)  |названию объекта или адрес <br> Тип:Observable `IPoint`|
