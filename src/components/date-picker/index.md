# DatePicker 时间选择器

时间选择器，可以选择日期和时间。

* `<DatePicker>`

> 当需要选择日期范围，推荐使用 [`<DateRangePicker>`](./date-range-picker)

## 获取组件

```js
import { DatePicker } from 'rsuite';
```

## 演示

<!--{demo}-->

## Props

### `<DatePicker>`

| 属性名称              | 类型`(默认值)`                                        | 描述                                                      |
| --------------------- | ----------------------------------------------------- | --------------------------------------------------------- |
| appearance            | enum: 'default', 'subtle' `('default')`               | 设置外观                                                  |
| block                 | boolean                                               | 堵塞整行                                                  |
| value                 | moment$Moment                                         | 值`受控`                                                  |
| defaultValue          | moment$Moment                                         | 默认值                                                    |
| calendarDefaultDate   | moment$Moment                                         | 日历面板默认呈现的日期时间                                |
| onChange              | (date:moment$Moment)=>void                            | 值改变后的回调函数                                        |
| onChangeCalendarDate  | (date: moment$Moment, event?: SyntheticEvent) => void | 日历日期改变后的回调函数                                  |
| onSelect              | (date:moment$Moment)=>void                            | 选择日期或者时间的回调函数                                |
| onOpen                | ()=>void                                              | 打开回调函数                                              |
| onClose               | ()=>void                                              | 关闭回调函数                                              |
| onToggleMonthDropdown | (open: boolean) => void                               | 切换到月份视图的回调函数                                  |
| onToggleTimeDropdown  | (open: boolean) => void                               | 切换到时间视图的回调函数                                  |
| onPrevMonth           | (date: moment$Moment) => void                         | 切换到上一月的回调函数                                    |
| onNextMonth           | (date: moment$Moment) => void                         | 切换到下一月的回调函数                                    |
| onOk                  | (date: moment$Moment, event: SyntheticEvent) => void  | 点击确定后的回调函数                                      |
| placeholder           | string                                                | 没有值时候默认显示内容                                    |
| format                | string `('YYYY-MM-DD')`                               | 日期显示格式化                                            |
| locale                | Object [`(Locale)`](#Locale)                          | 本地化对应的语言描述                                      |
| ranges                | Array<[Range](#Range)> [`(Ranges)`](#Ranges)          | 快捷项配置                                                |
| inline                | boolean                                               | 默认显示日历面板                                          |
| disabled              | boolean                                               | 禁用组件                                                  |
| disabledDate          | (date:moment$Moment)=>boolean                         | 禁用日期                                                  |
| disabledHours         | (hour:number, date:moment$Moment)=>boolean            | 禁用小时                                                  |
| disabledMinutes       | (minute:number, date:moment$Moment)=>boolean          | 禁用分钟                                                  |
| disabledSeconds       | (second:number, date:moment$Moment)=>boolean          | 禁用秒                                                    |
| hideHours             | (hour:number, date:moment$Moment)=>boolean            | 隐藏小时                                                  |
| hideMinutes           | (minute:number, date:moment$Moment)=>boolean          | 隐藏分钟                                                  |
| hideSeconds           | (second:number, date:moment$Moment)=>boolean          | 隐藏秒                                                    |
| cleanable             | boolean `(true)`                                      | 可以清除                                                  |
| isoWeek               | boolean                                               | ISO 8601 标准， 每个日历星期从星期一开始，星期日为第 7 天 |
| open                  | boolean                                               | 打开 (受控)                                               |
| defaultOpen           | boolean                                               | 默认打开                                                  |
| placement             | enum: [Placement](#Placement) `('bottomLeft')`        | 显示位置                                                  |
| limitStartYear        | number `(5)`                                          | 相对当前选择日期，设置可选年份上限                        |
| limitEndYear          | number `(5)`                                          | 相对当前选择日期，设置可选年份下限                        |
| menuClassName         | string                                                | 选项菜单的 className                                      |
| container             | HTMLElement or (() => HTMLElement)                    | 设置渲染的容器                                            |
| toggleComponentClass  | React.ElementType `('a')`                             | 为组件自定义元素类型                                      |

## Types

### Range

```js
type Range = {
  label: React.Node,
  closeOverlay?: boolean,
  value: moment$Moment | ((date: moment$Moment) => moment$Moment)
};
```

### Placement

```js
type Placement =
  | 'bottomLeft'
  | 'bottomRight'
  | 'topLeft'
  | 'topRight'
  | 'leftTop'
  | 'rightTop'
  | 'leftBottom'
  | 'rightBottom'
  | 'auto'
  | 'autoVerticalLeft'
  | 'autoVerticalRight'
  | 'autoHorizontalTop'
  | 'autoHorizontalBottom';
```

## Default

### Locale

```js
const Locale = {
  sunday: 'Su',
  monday: 'Mo',
  tuesday: 'Tu',
  wednesday: 'We',
  thursday: 'Th',
  friday: 'Fr',
  saturday: 'Sa',
  ok: 'OK',
  today: 'Today',
  yesterday: 'Yesterday',
  hours: 'Hours',
  minutes: 'Minutes',
  seconds: 'Seconds'
};
```

### Ranges

```js
const Ranges = [
  {
    label: 'today',
    value: moment$Moment(),
    closeOverlay: true
  },
  {
    label: 'yesterday',
    value: moment$Moment().add(-1, 'd'),
    closeOverlay: true
  }
];
```
