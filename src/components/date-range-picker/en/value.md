### Controlled


<!--start-code-->
```js
class DateRangePickerValue extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: [moment('2017-02-01'), moment('2017-05-20')]
    };
  }
  render() {
    return (
      <div className="field">
        <DateRangePicker
          value={this.state.value}
          onChange={(value) => {
            this.setState({ value });
          }}
        />
      </div>
    );
  }
}

ReactDOM.render(<DateRangePickerValue />);
```
<!--end-code-->
