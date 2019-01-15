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
