# CSV - JSON

CSV - JSON is designed to swap the formatting of CSV to JSON and vice versa.
It also holds a method that is designed to pull from an SQL database and be put in a JSON class.
# Installation

This project was built in the Netbeans IDE and contains Netbeans metadata.
That means it will work best within the Netbeans IDE.
Make sure to have the JSON-Simple, JUnit4.12, OpenCSV, and Hamcrest 1.3 installed inside your Netbeans IDE.

# Usage

csvtoJson takes in a comma seperated value string and returns a string that is formatted in JSON.
It does this by taking a special CSVReader object and creating an instance of it with a CSV.
It attaches an iterator to a list of all the CSVReader parts.
Those parts are each line. When the iterator cycles through, it goes to a new line.
Before going through the iterator it adds the first instance of the iterator as the header for the top via JSONArray.
It takes that iterator and add the headers for the row and put them in a special JSONArray.
It then takes the rest of the information and adds it as the body of the data for the JSON. 
It continues to loop through the iterator until it is through with the csv. 
It tethers the information together into a jsonString and then prints.

Before:
```
"ID","Total","Assignment 1","Assignment 2","Exam 1"
        "111278","611","146","128","337"
        "111352","867","227","228","412"
        "111373","461","96","90","275"
        "111305","835","220","217","398"
        "111399","898","226","229","443"
        "111160","454","77","125","252"
        "111276","579","130","111","338"
        "111241","973","236","237","500"
```
After:
```
"colHeaders":["ID","Total","Assignment 1","Assignment 2","Exam 1"],
            "rowHeaders":["111278","111352","111373","111305","111399","111160",
            "111276","111241"],
            "data":[[611,146,128,337],
                    [867,227,228,412],
                    [461,96,90,275],
                    [835,220,217,398],
                    [898,226,229,443],
                    [454,77,125,252],
                    [579,130,111,338],
                    [973,236,237,500]
            ]
```

jsonToCSV is a bit simpler. The JSON data

