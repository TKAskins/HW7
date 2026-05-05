# HW7
Repo for HW7

Environment: either activate conda and use 'conda env create -f environment.yml' to create "HW7_Environment" which after being created can be activated using 'conda activate HW7_Environment'

This can be slow so you can alternatively create a python virtual environment by using 'source HW7_Environment/bin/activate'

Once you have the enviroment active 'cd Week14_StreamflowForecast' will get you into the right place and then you will be ready to forecast!

Before forecsting you must edit the uder options in 'run_workflow.sh'. DO NOT EDIT ANYTHING OUTSIDE OF THE USER OPTION BLOCK! You can choose your guage, the date you want a forcast to start at, and the range of data you want to use to predict the forecast.

You will also need to choose between forecasting using longterm average, monthly averages, or recent trends. 

If you select longterm average your forecast will assign the cfs for each forecasted day to match the average cfs for that day for all past years in your training range. This basically forecasts the 'most likely' cfs, including the chance for things like precip for each date regardless of recent events.

If you select monthly average the forecast values will reflect the monthly average from the training range for each day forecasted. If your forecast falls all in the same month, all values will be the same. It forecast for 'most likely for this month'

If you select trend forecast your forecast will be driven off only the last ten days of the training data. This removes the impact/potential of things like precip but falls closer in line with recent events but means your training data has to be current.

If you have never forecasted before ensure re-train is set to 'true'. You cannot forecast without some training data set which is only produced if re-train is set to true. If you have trained the model before, are not switching forecating methods (IE: long term to trend), and believe your previous training range to still represent your new forecast date, save yourself time and set retrain to 'false'

Once user options have been set you can forecast using './run_workflow.sh' and you will have plots and values generated for future date using you selected modeling method!

**NOTE** You must have an active Hydroframe email and pin. You will enter these in the terminal after running the shell script. Dont worry, username and password is not saved.