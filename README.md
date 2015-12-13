# React Native Dropdown
Simple DropDown menu for React Native App! Your Select Tag for React Native. 

## Introduction

React Native Select is simple, customizable and easy to use dropdown in React Native. Works with both Android and IOS. 

## Installation
```
npm i react-native-select --save
```

## Usage
Require it inside your Javascript files. Also supporting components using object-deconstructing. 
```Select``` ```Option``` ```OptionList```.

```<OptionList />``` Is to be used to append the options. This has to be placed as a last component so that it take the highest Z-Index.

## Example

```
var React = require('react-native');
var {
  Component,
  AppRegistry,
  Text,
  View,
} = React;

const DropDown = require('react-native-select');
const {
  Select,
  Option,
  OptionList
} = DropDown;

class App extends Component {
  constructor(props) {
    super(props);

    this.state = {
      canada: ''
    };
  }

  _getOptionList() {
    return this.refs['OPTIONLIST'];
  }

  
  _canada(province) {

	this.setState({
      ...this.state,
      canada: province
    });
  }

  render() {
    return (
      <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Select
            width={250}
            ref="SELECT1"
            optionListRef={this._getOptionList.bind(this)}
            defaultValue="Select a Province in Canada ..."
            onSelect={this._canada.bind(this)}>
            <Option>Alberta</Option>
            <Option>British Columbia</Option>
            <Option>Manitoba</Option>
            <Option>New Brunswick</Option>
            <Option>Newfoundland and Labrador</Option>
            <Option>Northwest Territories</Option>
            <Option>Nova Scotia</Option>
            <Option>Nunavut</Option>
            <Option>Ontario</Option>
            <Option>Prince Edward Island</Option>
            <Option>Quebec</Option>
            <Option>Saskatchewan</Option>
            <Option>Yukon</Option>
          </Select>

          <Text>Selected Canada's province: {this.state.canada}</Text>
          
          <OptionList ref="OPTIONLIST"/>
      </View>
    );
  }
}

AppRegistry.registerComponent('App', () => App);


```
For complete implementation checkout example folder. 

### Configuration

##### Select:
| Property | Type | Default | Description |
|---------------|----------|--------------|----------------------------------------------------------------|
| style | number | 400 | Width of the selection |
| height | number | 50 | Height of the selection |
| optionListRef | function | required | Reference to ```<OptionList />``` to display the selection menu |
| style | object | null | Custom styles to be applied if supplied |
| defaultValue | string | first option | The value to be displayed if none of the options are selected. |

##### Option:

| Property | Type | Default | Description |
|-----------|--------|---------|--------------------------------------------|
| style | object | null | Styles to be applied on 'Option' component |
| styleText | object |  null | Styles to be applied on text inside of 'Option'  |


## Demo
#####  IOS:
<p align="center">
    <img src ="https://github.com/gs-akhan/react-native-select/blob/master/dropdown.gif" />
</p>

#####  Android:
<p align="center">
    <img src ="https://github.com/gs-akhan/react-native-select/blob/master/dropdown-android.gif" />
</p>