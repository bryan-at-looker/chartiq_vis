looker.plugins.visualizations.add({
  // Id and Label are legacy properties that no longer have any function besides documenting
  // what the visualization used to have. The properties are now set via the manifest
  // form within the admin/visualizations page of Looker
  id: "hello_world",
  label: "Hello World",
  // Set up the initial state of the visualization
  create: function(element, config) {

    // Insert a <style> tag with some styles we'll use later.
    element.innerHTML = `
      <style>
        .chartContainer {
          /* Vertical centering */
          height: 100%;
          display: flex;
          flex-direction: column;
          justify-content: center;
          text-align: center;
        }
      </style>
    `;

    // Create a container element to let us center the text.
    var container = element.appendChild(document.createElement("div"));
    container.className = "chartContainer";
    container.id = "chartiq";

    // Create an element to contain the text.
    this._textElement = container.appendChild(document.createElement("div"));

  },
  // Render in response to the data or settings changing
  updateAsync: function(data, element, config, queryResponse, details, done) {

    // Clear any errors from previous updates
    this.clearErrors();

    var container = document.getElementById('chartiq')

    // Throw some errors and exit if the shape of the data isn't what this chart needs
    // if (queryResponse.fields.dimensions.length == 0) {
    //   this.addError({title: "No Dimensions", message: "This chart requires dimensions."});
    //   return;
    // }

    // Grab the first cell of the data
    // var firstRow = data[0];
    // var firstCell = firstRow[queryResponse.fields.dimensions[0].name];

    // Insert the data into the page
    // this._textElement.innerHTML = LookerCharts.Utils.htmlForCell(firstCell);

    // Declare a CIQ.ChartEngine object.
    // This is the main object for drawing charts.
    // Here is where you set all required defaults.

    var stxx = CIQ.ChartEngine({
      container: container,
      layout: {
        "chartType": "candle",
        "crosshair": true,
        "candleWidth": 30,
        "periodicity": 1,
        "interval": 'day',
      },
      preferences: {
        "currentPriceLine": true,
        "whitespace": 100
      },
      chart: {
        yAxis: {
          position: 'left'
        }
      }
    });

    //Now load a chart with it's data
    stxx.loadChart(
      "SPY", [{
        "Date": "1993-01-29",
        "Open": 43.97,
        "High": 43.97,
        "Low": 43.75,
        "Close": 43.94,
        "Volume": 1003200,
        "Adj_Close": 31.16
      }, {
        "Date": "1993-02-01",
        "Open": 43.97,
        "High": 44.25,
        "Low": 43.97,
        "Close": 44.25,
        "Volume": 480500,
        "Adj_Close": 31.38
      }, {
        "Date": "1993-02-02",
        "Open": 44.22,
        "High": 44.38,
        "Low": 44.13,
        "Close": 44.34,
        "Volume": 201300,
        "Adj_Close": 31.44
      }, {
        "Date": "1993-02-03",
        "Open": 44.41,
        "High": 44.84,
        "Low": 44.38,
        "Close": 44.81,
        "Volume": 529400,
        "Adj_Close": 31.77
      }, {
        "Date": "1993-02-04",
        "Open": 44.97,
        "High": 45.09,
        "Low": 44.47,
        "Close": 45,
        "Volume": 531500,
        "Adj_Close": 31.91
      }, {
        "Date": "1993-02-05",
        "Open": 44.97,
        "High": 45.06,
        "Low": 44.72,
        "Close": 44.97,
        "Volume": 492100,
        "Adj_Close": 31.89
      }, {
        "Date": "1993-02-08",
        "Open": 44.97,
        "High": 45.13,
        "Low": 44.91,
        "Close": 44.97,
        "Volume": 596100,
        "Adj_Close": 31.89
      }, {
        "Date": "1993-02-09",
        "Open": 44.81,
        "High": 44.81,
        "Low": 44.56,
        "Close": 44.66,
        "Volume": 122100,
        "Adj_Close": 31.67
      }, {
        "Date": "1993-02-10",
        "Open": 44.66,
        "High": 44.75,
        "Low": 44.53,
        "Close": 44.72,
        "Volume": 379600,
        "Adj_Close": 31.71
      }]
    );

    // We are done rendering! Let Looker know.
    done()
  }
});zgit commit -m "first commit"
