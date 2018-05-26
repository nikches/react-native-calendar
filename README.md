# react-native-calendar

This is a minor update.
The new feature this release adds is simply so that the calendar component can also receive a `style` props in order to customize the default styling.

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
import { StyleSheet } from "react-native";

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
                onDateSelect={(date) => this.handleDateSelect(date)}
                style={{styles.customStyling}} />
        );
    }
}

const styles = StyleSheet.create({
    customStyling: {
        borderBottomWidth: 0
    }
})
```
