# Traffic_Prediction
Traffic Prediction, BCG Datathon 12.2020

The aim of this project is to develop a model that predicts the traffic (occupation rate of streets) in Paris.

Steps to execute to run the project from the start:
--------------------------------------------------
--------------------------------------------------
step1:
------
- Visit the following URL to download the CSV files for the selected roads:
	* https://opendata.paris.fr/explore/dataset/comptages-routiers-permanents/export/?disjunctive.libelle&disjunctive.etat_trafic&disjunctive.libelle_nd_amont&disjunctive.libelle_nd_aval&sort=t_1h
- Then rename them and place them under the folder "datasets". The name should be "washington_new.csv"


- Fill the csv file template_x_pred.csv and fill it out with the desired values for the prediction. 
For that use the following links:
	* https://covidtracker.fr/
	* google for the weather forecast for t_min and t_max (e.g. use https://weather.com/weather/tenday/l/724a03c48ba53e3e5acee3b6d8a63717a02e1635413b129ca7a3dc0ff1ab895e#detailIndex5 )

- For training purposes use the following link to replace the file "table-indicateurs-open-data-france.csv". 
For that use the following link:
	* https://www.data.gouv.fr/fr/datasets/indicateurs-de-suivi-de-lepidemie-de-covid-19/?fbclid=IwAR1TGLH7MDWlb_Jm3aSxTCgyBrm7VL4o3e_3837zwY_DxUo1GlHdmVElt_U


Step2:
------
- Use preprocessing.ipynb (3 times) to preprocess the CSV files downloaded. 
At the end one should have the following 3 files in the folder "datasets":
	* "washington_edited.csv"
	* "convention_edited.csv"
	* "sts_edited.csv"

Step3: 
------
- Use prepare_x_pred.ipynb (3 times) to get the needed x values for the prediction.
At the end, one should have the following files:
	* "x_pred_washington.csv"
	* "x_pred_convention.csv"
	* "x_pred_sts.csv"

(Optional step):
----------------
- One can try out different hyperparameter & feature options. This is done with the notebook "models.ipynb". 
New folders will be created (washington, convention and sts)

Step4: 
------
- Use "model_selection.ipynb" to visualize the best hyperparameter & feature combinations. In the end, pick one / the best
combination and keep it in mind.


Step5:
------
- Use "predict_results.ipynb" 6 times to have the wanted results. To do that, enter the  one / the best
hyperparameter & feature combination.

At the end, you should have 6 CSV files:
	* "result_pred_washington_Taux d'occupation.csv"
	* "result_pred_washington_Débit horaire.csv"
	* "result_pred_convention_Taux d'occupation.csv"
	* "result_pred_convention_Débit horaire.csv"
	* "result_pred_sts_Taux d'occupation.csv"
	* "result_pred_sts_Débit horaire.csv"

Step6: 
------
- Aggregate all results using the notebook "result_aggregation".
Afterwards, one should have a new file "output.csv" including all the results
