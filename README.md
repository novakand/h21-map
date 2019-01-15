# Angular Модуль Maps


### `Компоненты:`

#### `h21-map:`

##### `Подключение и использование:`
```javascript

<h21-map 
[latitude]="27.215556209029693" 
[longitude]="18.45703125" 
[zoom]="3" 
(mapReady)="mapReadu($event)" 
(mapClick)="mapClick($event)"
(mapMouseMove)="mapMouseMove($event)">
</h21-map>

```

```javascript
import { H21MapsComponent } from "/h21-map/h21-map.component";

@ViewChild(H21MapsComponent) public maps: H21MapsComponent;

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
| defaultCursor       | Выбранный курсор на карте <br> Тип: CursorType   <br> Значение по умолчанию: `CursorType.default`

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
| geolocationChange       | Это событие вызывается когда был осуществлен запрос на геопозиции  . <br> Тип: string   |
| geolocationChange       | Это событие вызывается когда был осуществлен запрос на геопозиции  . <br> Тип: string   |
