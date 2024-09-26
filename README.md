     #We cloned the repository after forking it
     git clone https://github.com/dduru26/learn_linux_by_doing.git
 
     cd learn_linux_by_doing

 .   #we made a git branch
     git checkout -b "group-analysis"
 
     cd data

     #We removed the test file
     rm test-1

     #We moved the top 5 highest temperature file to the analyzed directory
     mv top5-highest-temperatures.csv analyzed/
  
     cd analyzed

     #We renamed the top5 highest temperatures file to top_5 highest temperature
     mv top5-highest-temperatures.csv top-5-highest-temperatures.csv
 
     cd ..
 
     cd data

     #we removed duplicate temparature data in this csv file
     sort satelite_temperature_data.csv | uniq > cleaned_satelite_temperature_data.csv
     ls
     cat satelite_temperature_data.csv

     #we sorted the data in descending order (highest to lowest) and exteracted the top 5 to a csv file in the analyzed directory
     sort -t "," -k3 -nr satelite_temperature_data.csv | head -n 5 > ../analyzed/top-5-highest-temparatures.csv
     cat satelite_temperature_data.csv
     cd ..
     cd analyzed
     ls
     cd ..
     cd data

     #we sorted the data in ascending order (lowest to highest) and exteracted the top 5 to a csv file in the analyzed directory
     sort -t "," -k3 -n satelite_temperature_data.csv | head -n 5 > ../analyzed/top-5-lowest-temparatures.csv
     cat ../analyzed/top-5-lowest-temparatures.csv
     ls

     #we sorted data for Rwanda and put it in a csv file in the analyzed directory
     grep "Rwanda" satelite_temperature_data.csv > ../analyzed/rwanda-heat_data.csv

     #we sorted data for South Sudan and put it in a csv file in the analyzed directory
     grep "South Sudan" satelite_temperature_data.csv > ../analyzed/southsudan-heat_data.csv

     #we sorted data for Nigeria and put it in a csv file in the analyzed directory
     grep "Nigeria" satelite_temperature_data.csv > ../analyzed/Nigeria-heat_data.csv
     cat ../analyzed/rwanda-heat_data.csv
     cat ../analyzed/southsudan-heat_data.csv
     cat ../analyzed/Nigeria-heat_data.csv
     cd ..
     ls
     emacs README.md
     history > README.md
