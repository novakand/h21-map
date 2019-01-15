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
| Inputs
                |                                                                                      Описание                                                                                      |
|-----------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| CallbackName.onclickMapPlaceId, (placeId) =>              | Событие происходит при клике по карте (по poi point google maps), метод возвращает placeId;                                                                                        |
| CallbackName.onclickMapCoordinates, (position) =>         | Событие происходит при клике по карте, метод возвращает координаты;                                                                                                                |
| CallbackName.detailsAddressResultPoint, (point) =>        | Метод возвращает point (IPoint), callback происходить при обращении к методу getDetailsPoint(placeId: string);                                                                     |
| CallbackName.geocoderAddressResult, (point) =>            | Метод возвращает объект point (IPoint),callback происходит при обращении к методу getAddress(position: IPosition);                                                                 |
| CallbackName.searchResult, (arrayPoint) =>                | Метод возвращает массив point (IPoint),callback происходит при обращении к методу getAddress(position: IPosition);                                                                 |
| CallbackName.searchDetailsResult, (point) =>              | Метод возвращает объект point (IPoint),callback происходит при обращении к методу searchDetails(placeId: string);                                                                  |
| callbackMap.on(CallbackName.changedBoundsMap, (bounds) => | Метод вызывается при каждом изменении границ области видимости экрана                                                                                                              |
| CallbackName.initMap, (status) =>                         | Метод вызывается при инициализации карты                                                                                                                                            |
| CallbackName.responseMapError, (status) =>                | Метод вызывается когда возникает ошибка у провайдера карт (возвращается статус ошибки)                                                                                             |
| CallbackName.createRadius, (infoCicle) =>                 | Метод вызывается когда добавлен круг на карту (метод возвращает информацию о круге: -радиус -координаты центра круга                                                               |
| CallbackName.radiusChanged, (infoCicle) =>                | Метод вызывается когда изменен размер радиуса (метод возвращается информацию о круге -радиус -координаты центра круга                                                              |
| CallbackName.radiusDragEnd, (infoCicle) =>                | Метод вызывается когда изменен круг закончили перетаскивать на карте (метод возвращается информацию о круге  -радиус  -координаты центра круга                                     |
| CallbackName.drawAreaStart, (position) =>                 | Метод вызывается когда начали рисовать произвольную область на карте                                                                                                               |
| CallbackName.drawAreaDragEnd, (arrayCoordinates) =>       | Метод вызывается когда начали закончили рисовать произвольную область на карте (метод возвращает массив координат)                                                                 |
| CallbackName.countLoadMarkers, (countLoadMarkers) =>      | Метод вызывается при добавлении маркеров на карту (метод возвращает количество загруженных точек на карте)                                                                         |
| CallbackName.markerClick, (pointId) =>                    | Метод вызывается при клике на маркер (метод возвращает id выбранного маркера)                                                                                                      |
| CallbackName.markerDraggableEnd, (infoMarker) =>          | Метод вызывается когда маркер закончили перетаскивать (метод возвращает информацию о маркере:  -position;                                                                          |
| CallbackName.markerDraggable, (infoMarker) =>             | Метод вызывается когда сработал метод setDraggableMarker() (метод возвращает информацию о маркере:   -разрешено/запрещено перетаскивать маркер;                                    |
| CallbackName.infoRoute, (infoRoute) =>                    | Метод вызывается когда был построен маршрут на карте (метод возвращает информацию о маршруте (от начальной до конечной точки): о дистанции, времени в пути с учетом пробок или без |

