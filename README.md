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
| enableDefaultControl       |Включает/ отключает, по умолчанию панели управления на карте ( По умолчанию только подключен контроль масштабирования) <br> Тип: boolean   <br> Значение по умолчанию: true

