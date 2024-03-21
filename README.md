Run the Process
0. my process file is ge32kik.xml on process hub
1. run the server.py file in terminal
2. in the CPEE, keep 'dd=0' in data element, and start running
3. after flight status changes to 'BRD', data start to be recorded and visualized
  3.1 weather data is stored in weather_csv.csv
  3.2 air quality data is stored in air_csv.csv
  3.3 run-time visualization can be seen at https://lehre.bpm.in.tum.de/~ge32kik/prak/v.html
4. CPEE process and visualization ends automatically 11 minutes after the flight's departure
5. See the comparison picture
   5.1 run compare_csv.py to see the comparison of average weather and air quality metrics during different flights
       (Many CSV files input allowed, only with CSV files named with weather and air).
       The output picture is called output.png
   5.2 run compare_air_pollutants_polyline_night.py to see the comparison of weather and air pollutants concentration change during the same flight
       (Only 3 CSV file input is allowed).
       The output pictures are called 'KL1027_Air_Pollutants_Comparison.png' and 'KL1027_Temperature_Humidity_Comparison.png'
   All the output pictures can be seen in the chosen output path. How to change the output path in Note 5.

Note:
1. Sometimes the Schiphol Airport API might not return a suitable plane for the process  ->  Try another time to run the process, 6:30 am to 8:00 pm is usually good;
2. The weather data is stored by default in the "weather.csv" file; The air quality data is stored by default in the 'air.csv' file;
   Want to start a new CSV file  ->  Change the file name in server.py: in function def record(), line 94, 95, 122, 123; The file name should start with weather and air;
3. Visualization can not be seen after the flight starts boarding  ->  wait for 5-15 seconds and refresh the webpage;
4. Cannot find the output comparison pictures after running compare_csv.py and compare_air_pollutants_polyline_night.py
   -> for compare_csv.py: change folder_path in line 67 to the directory you want to show the output
   -> for compare_air_pollutants_polyline_night.py: output path is default set to output_path='KL1027_Temperature_Humidity_Comparison.png' and output_path='KL1027_Air_Pollutants_Comparison.png',
      need to add new output path in line 120, 121;
5. change csv_path_1, csv_path_2, csv_path_3 to other air data files in line 112-114 to show new air quality comparison picture in compare_air_pollutants_polyline_night.py
   change csv_path_w1, csv_path_w2, csv_path_w3 to other weather data files to show new comparison in compare_air_pollutants_polyline_night.py
