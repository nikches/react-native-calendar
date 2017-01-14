# react-native-calendar
Calendar component for ReactNative. It is stateless component.

![example](calendar.png)

## install 
```
npm install --save react-native-calendar-component
```

## props
|  prop              | type     | default value                |
|--------------------|----------|------------------------------|
| date               | Date     | new Date()                   |
| onDateSelect       | function | null                         |
| onPrevButtonPress  | function | null                         |
| onNextButtonPress  | function | null                         |
| dayNames           | array    | ["Sun", "Mon" ... ]          |
| monthNames         | array    | ["January", "February" ... ] |
| weekFirstDay       | number   | 0                            |

## usage
```javascript
<Calendar
    date={this.state.date}
    onPrevButtonPress={() => this.handlePrevButtonPress()}
    onNextButtonPress={() => this.handleNextButtonPress()}
    onDateSelect={(date) => this.handleDateSelect(date)} />
```
