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
| setCircleEditable    | setCircleEditable (enabled) <br> Parameters: <br> <li>enabled: boolean </li> Return Value :  <li>None</li> Установить редактирование окружности (радиуса) <br> Если `enabled` значение true, радиус можно редактировать. Значение по умолчанию - false.              |
| setCircleRadius      | setCircleRadius(radius) Parameters: <br> <li>radius: number </li> Return Value :  <li>None</li> Установить у окружности радиус <br> Радиус окружности нужно установить в метрах                                                                                      |
| setCircleDraggable   | setCircleDraggable(enabled) <br> Parameters: <br> <li>enabled: boolean </li> Return Value :  <li>None</li> Установить перемещение окружности по карте <br> Если `enabled` значение true, радиус можно перемещать по карте. Значение по умолчанию - false.            |
| setBindCicleToMarker | setBindCicleToMarker()<br> Arguments : None <br> Установить привязку окружности (радиуса) к маркеру,при перемещении маркера, окружность будет перемещаться с выбранным маркером <br> `Должен быть выбран selectedMarker `                                            |
| setLoadMarkers       | setLoadMarkers(enabled) <br> Parameters: <br> <li>enabled: boolean </li> Return Value : <li> None </li> Установить разрешение на загрузку точек в видимой области карты  <br> Если `enabled` значение true, загрузка разрешена. Значение по умолчанию - true.        |
| clearAllMap          | clearAllMap()<br> Arguments :  <li>None </li> Удалить все объекты с карты                                                                                                                                                                                            |
| clearMarkers         | clearMarkers()<br> Arguments : <li>None </li>  Удалить все маркеры с карты                                                                                                                                                                                           |
| clearRoutes          | clearRoutes()</br> Arguments :  <li>None </li> Удалить все построенные маршруты с карты                                                                                                                                                                              |
| clearPolygons        | clearPolygons()</br> Arguments :  <li>None </li> Удалить все полигоны с карты                                                                                                                                                                                        |
| clearCircle          | clearCircle()</br> Arguments :  <li>None </li> Удалить окружность с карты                                                                                                                                                                                            |
| zoomIn               | zoomIn()</br> Arguments : <br> </li>None <li> Увеличивает масштаб на 1 позицию                                                                                                                                                                                       |
| zoomOut              | zoomOut() <br> Arguments :  <li>None </li>  Уменьшить масштаб на 1 позицию                                                                                                                                                                                           |
| getLoadCountMarker   | getLoadCountMarker() <br> Arguments :  <li>None </li> Получить количество загруженных маркеров на карте                                                                                                                                                              |
| getAddress           | getAddress(position) Parameters: <br> <li>position: IPosition</li> Return Value : <li> None </li> callback Value :  <li>point:IPoint<li> Получение детальной информации о точке на основе переданных координат                                                       |
| getDetailsPoint      | getDetailsPoint(placeId)  <br> Parameters: <br> <li>placeId: string</li> Return Value :  <li>None </li> callback Value :  <li>point:IPoint<li> Получение детальной информации о точке на основе переданных place Id (идентификатор места google maps)                |
| getZoom              | getZoom() <br> Arguments : <li> None </li> Return Value : </li> number </li> Получение текущего масштаба карты                                                                                                                                                       |
| getBounds            | getBounds() <br> Arguments : <li> None </li> Return Value : <li> ILatLngBounds </li> Возвращает географические координаты видимого участка карты                                                                                                                     |
| getCenter            | getCenter() <br> Arguments : <li> None </li> Return Value : <li> ILatLng</li> Возвращает географические координаты центральной точки карты                                                                                                                           |
| setZoom              | setZoom(zoom)  <br> Parameters: <br> <li>zoom: number</li> Return Value :  <li>None</li> Установить масштаб на карте                                                                                                                                                 |
| setMinZoom           | setMinZoom() <br> Parameters: <br> <li>zoom: number</li> Return Value :  <li>None</li> Установить минимальный масштаб на карте                                                                                                                                       |
| setMaxZoom           | setMaxZoom() <br> Parameters: <br> <li>zoom: number</li> Return Value :  <li>None</li> Установить максимальный масштаб на карте                                                                                                                                      |
| setCenter            | setCenter() <br> Parameters: <br> <li>position: IPosition</li> Return Value :  <li>None</li> Установить центр карты                                                                                                                                                  |
| setClikMap           | setClikMap(enabled) <br> Parameters: <br> <li>enabled: boolean </li> Return Value : <li> None </li> Установить разрешение на событие клика по карте <br> Если `enabled` значение true, клик разрешен. Значение по умолчанию - false.                                 |
| getRouteInfo         | getRouteInfo() <br> Arguments : <li> None </li> Return Value : <li> IRouteInfo</li> Возвращает информацию о построенном маршруте                                                                                                                                     |
| search               | search(query) <br> Parameters: <br> <li>query: string</li> Return Value : <li> Array <IPoint ></li> Поиск на карте <br>                                                                                                                                              |
| searchDetails        | searchDetails(placeId) <br> Parameters: <br> <li>query: string</li> Return Value : <li> Array <IPoint></li> Observable: <li><IPoint></li> callback: <li>IPoint</li> Получение детальной информации о точке поиска на основе placeId  <br>                            |
| getSelectedMarker    | getSelectedMarker() <br> Arguments :  <li> None </li> Return Value : <li>BaseMarker</li> Возвращает выбранный маркер                                                                                                                                                 |
| setSelectedMarker    | setSelectedMarker(marker) <br> Parameters: <br> <li>marker: BaseMarker</li> Return Value : <li> None <IPoint></li> Установить выбранный маркер <br>                                                                                                                  |
| resizeMap            | resizeMap(onCenter) <br> Parameters: <br> <li>onCenter: boolean</li> Return Value : <li> None</li> Можно вызвать данный метод при изменении размеров контейнера карты <br> `onCenter`выставить карту по центру                                                       |
| toggleMapDragging    | toggleMapDragging(enabled) <br> Parameters: <br> <li>enabled: boolean</li> Return Value : <li> None</li> Перемещение по карте <br> Если `enabled` значение true, перемещение по карте разрешено. Значение по умолчанию - true.                                       |
| setDraggableMarker   | setDraggableMarker(enabled) <br> Parameters: <br> <li>enabled: boolean</li> Return Value : <li> None</li> Перемещение маркера по карте <br> Если `enabled` значение true, перемещение маркера по карте разрешено. Значение по умолчанию - false.                     |
| toggleTrafficLayer   | toggleTrafficLayer(show) <br> Parameters: <br> <li>show: boolean</li> Return Value : <li> None</li> Показать на карте слой с дорожно-транспортной информацией. <br> Если `enabled` значение true, слой показан на карте. Значение по умолчанию - false.              |
| toggleTransitLayer   | toggleTransitLayer(show) <br> Parameters: <br> <li>show: boolean</li> Return Value : <li> None</li> Показать на карте слой общественного транспорта. <br> Если `enabled` значение true, слой показан на карте. Значение по умолчанию - false.                        |
