# react-native-calendar

This is basically an update to Nikches' React Native Calendar Component. The reason for the update is to solve the errors due to the deprecation of React.PropTypes.
Basic usage is generally/exactly the same

Calendar component for ReactNative. It is stateless component.

![example](calendar.png)

## install 
```
npm install --save react-native-calendar-updated
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
import React, { Component } from "react";
import Calendar from "react-native-calendar-updated";

export default class CalendarTest extends Component {
    constructor(props) {
        super(props);

        this.state = {
            date: new Date()
        };
    }

    handleNextButtonPress() {
        const date = new Date(this.state.date);
        date.setMonth(date.getMonth() + 1);
        this.setState({
            date
        });
    }

    handlePrevButtonPress() {
        const date = new Date(this.state.date);
        date.setMonth(date.getMonth() - 1);
        this.setState({
            date
        });
    }

    handleDateSelect(date) {
        alert(`clicked: ${this.state.date.toString()}`);
    }

    render() {
        return (
            <Calendar
                date={this.state.date}
                onPrevButtonPress={() => this.handlePrevButtonPress()}
                onNextButtonPress={() => this.handleNextButtonPress()}
                onDateSelect={(date) => this.handleDateSelect(date)} />
        );
    }
}
```
