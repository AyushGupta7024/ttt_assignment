WordHistogram
The WordHistogram is a React component that fetches text data from an API endpoint, generates a histogram of the word frequencies, and displays it using Chart.js. The histogram shows the top 20 most frequent words in the fetched text data.

Getting Started
To use the WordHistogram component, follow these steps:

Clone the repository or copy the WordHistogram component code into your React project.

Install the required dependencies by running the following command:
npm install chart.js
3.Import the WordHistogram component into your React application.
import WordHistogram from './WordHistogram';
4.Add the WordHistogram component to your React component hierarchy.
```
import './App.css';
import WordHistogram from './histogram';
function App() {
  return (
    <div className="App">
      <WordHistogram />
    </div>
  );
}
export default App;
```
5.Customize the WordHistogram component as needed, such as modifying the button styles or chart options.
6.Start your React application and view the WordHistogram component in your browser.
npm start
Functionality
The WordHistogram component provides the following functionality:

Fetching Text Data: When the "Submit" button is clicked, the component fetches text data from the specified API endpoint (https://www.terriblytinytales.com/test.txt).
//code here
const fetchData = async () => {
    const response = await fetch("https://www.terriblytinytales.com/test.txt");
    const textData = await response.text();
    const words = textData.match(/\b\w+\b/g);
    const frequency = {};
    words.forEach((word) => {
      const lowercaseWord = word.toLowerCase();
      if (frequency[lowercaseWord]) {
        frequency[lowercaseWord]++;
      } else {
        frequency[lowercaseWord] = 1;
      }
    });

Word Frequency Calculation: The fetched text data is processed to calculate the frequency of each word using regular expressions. The frequencies are then sorted in descending order.

Histogram Generation: The top 20 most frequent words and their frequencies are used to generate a bar chart using Chart.js. The chart is displayed in the component once it's visible.

Exporting Data: After the chart is visible, you can click the "Export" button to export the histogram data as a CSV file. The data is downloaded with the filename "histogram.csv".
Dependencies
The WordHistogram component depends on the following libraries:

React: A JavaScript library for building user interfaces.
Chart.js: A charting library that provides an easy way to visualize data using various chart types.

File Structure
The WordHistogram component consists of the following files:

WordHistogram.js: The main component file that contains the WordHistogram component code.
WordHistogram.css: The CSS file that provides styles for the WordHistogram component.

Customization
You can customize the WordHistogram component by modifying the CSS styles in the WordHistogram.css file. Additionally, you can adjust the chart options and appearance by modifying the generateChart function in the component code.
Contributing
Contributions to the WordHistogram component are welcome! If you find any issues or have suggestions for improvement, please open an issue or submit a pull request to the GitHub repository.
