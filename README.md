import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import streamlit as st
weather_df=pd.read_csv('/content/weatherHistory.csv')
weather_df.rename(columns={'Temperature (C)':'Temperature_c'},inplace=True)
weather_df.rename(columns={'Apparent Temperature (C)':'Apparent_Temperature_c'},inplace=True)
weather_df.rename(columns={'Wind Speed (km/h)':'Wind_speed_km_per_hour'},inplace=True)
weather_df.rename(columns={'Wind Bearing (degrees)':'Wind_Bearing_degrees'},inplace=True)
weather_df.rename(columns={'Visibility (km)':'Visibility_km'},inplace=True)
weather_df.rename(columns={'Loud Cover':'Loud_Cover'},inplace=True)
weather_df.rename(columns={'Pressure (millibars)':'Pressure_millibars'},inplace=True)
weather_df.rename(columns={'Daily Summary':'Daily_Summary'},inplace=True)
print(weather_df)
print(f"the dimensions of the weather data frame is:{weather_df.shape}")
x=int(input("Enter no.of rows you want:"))
print(f"the first  rows are: \n {weather_df.head(x)}")
column= weather_df[input("enter the column:")].nunique()
print(column)
unique_values=weather_df[input("once again enter column name:")].unique()
print(f"These are the unique value:\n {unique_values}")
null_values=weather_df.isnull().sum()
print(f"The no.of null values of each column:\n{null_values}")
print(f"The mean of humidity is:{weather_df.Humidity.mean()}")
print(f"The mean of Temperature is:{weather_df.Temperature_c.mean()}")
print(f"The mean of apparent Temperature is:{weather_df.Apparent_Temperature_c.mean()}")
print(f"The mean of wind speed is:{weather_df.Wind_speed_km_per_hour.mean()}")
print(f"The mean of wind bearings is:{weather_df.Wind_Bearing_degrees.mean()}")
print(f"The mean of visibility is:{weather_df.Visibility_km.mean()}")
print(f"The mean of loud cover is:{weather_df.Loud_Cover.mean()}")
print(f"The mean of pressure is:{weather_df.Pressure_millibars.mean()}")
print(f"The SD of humidity is:{weather_df.Humidity.std()}")
print(f"The SD of Temperature is:{weather_df.Temperature_c.std()}")
print(f"The SD of apparent Temperature is:{weather_df.Apparent_Temperature_c.std()}")
print(f"The SD of wind speed is:{weather_df.Wind_speed_km_per_hour.std()}")
print(f"The SD of wind bearings is:{weather_df.Wind_Bearing_degrees.std()}")
print(f"The SD of visibility is:{weather_df.Visibility_km.std()}")
print(f"The SD of loud cover is:{weather_df.Loud_Cover.std()}")
print(f"The SD of pressure is:{weather_df.Pressure_millibars.std()}")
col_index=int(input("enter the column index:"))
column=weather_df.iloc[:,w]
print(f"The values are:{weather_df.value_counts(column)}")
#BARGRAPHS USING MATPLOTLIB
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
temp=weather_df.iloc[:,3]
app_temp=weather_df.iloc[:,4]
plt.xlabel("Temperature(c)")
plt.ylabel("Apparent Temperature(c)")
plt.bar(temp,app_temp)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
temp=weather_df.iloc[:,3]
humid=weather_df.iloc[:,5]
plt.xlabel("Temperature(c)")
plt.ylabel("Humidity")
plt.bar(temp,humid)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
temp=weather_df.iloc[:,3]
windspeed=weather_df.iloc[:,6]
plt.xlabel("Temperature")
plt.ylabel("Windspeed(km/h)")
plt.bar(temp,windspeed)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
temp=weather_df.iloc[:,3]
wind_bearing=weather_df.iloc[:,7]
plt.xlabel("Temperature(c)")
plt.ylabel("wind bearing(degrees)")
plt.bar(temp,wind_bearing)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
temp=weather_df.iloc[:,3]
visibility=weather_df.iloc[:,8]
plt.xlabel("Temperature(c)")
plt.ylabel("visibility(km)")
plt.bar(temp,visibility)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
temp=weather_df.iloc[:,3]
pressure=weather_df.iloc[:,10]
plt.xlabel("Temperature(c)")
plt.ylabel("pressure(millibars)")
plt.bar(temp,pressure)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
app_temp=weather_df.iloc[:,4]
humid=weather_df.iloc[:,5]
plt.xlabel("Apparent Temperature(c)")
plt.ylabel("Humidity")
plt.bar(app_temp,humid)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
app_temp=weather_df.iloc[:,4]
windspeed=weather_df.iloc[:,6]
plt.xlabel("ApparentTemperature(c)")
plt.ylabel("Wind speed(km/h)")
plt.bar(app_temp,windspeed)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
app_temp=weather_df.iloc[:,4]
wind_bearing=weather_df.iloc[:,7]
plt.xlabel("Apparent Temperature(c)")
plt.ylabel("Wind bearing(degrees)")
plt.bar(app_temp,wind_bearing)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
app_temptemp=weather_df.iloc[:,4]
visibility=weather_df.iloc[:,8]
plt.xlabel("Apparent Temperature(c)")
plt.ylabel("Visibility(km)")
plt.bar(app_temp,visibility)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
app_temp=weather_df.iloc[:,4]
pressure=weather_df.iloc[:,10]
plt.xlabel("Apparent Temperature(c)")
plt.ylabel("pressure(millibars)")
plt.bar(app_temp,pressure)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
humidity=weather_df.iloc[:,5]
windspeed=weather_df.iloc[:,6]
plt.xlabel("Humidity")
plt.ylabel("Wind speed(km/h)")
plt.bar(humidity,windspeed)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
humidity=weather_df.iloc[:,5]
windbearing=weather_df.iloc[:,6]
plt.xlabel("Humidity")
plt.ylabel("Wind bearings(degrees)")
plt.bar(humidity,windbearing)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
humidity=weather_df.iloc[:,5]
visibility=weather_df.iloc[:,8]
plt.xlabel("Humidity")
plt.ylabel("Visibility(km/h)")
plt.bar(humidity,visibility)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
humidity=weather_df.iloc[:,5]
pressure=weather_df.iloc[:,10]
plt.xlabel("Humidity")
plt.ylabel("Pressure(millibars)")
plt.bar(humidity,pressure)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
windbearing=weather_df.iloc[:,7]
windspeed=weather_df.iloc[:,6]
plt.xlabel("Wind speed(km/h)")
plt.ylabel("Windbearing(degrees)")
plt.bar(windspeed,windbearing)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
visibility=weather_df.iloc[:,8]
windspeed=weather_df.iloc[:,6]
plt.xlabel("Wind speed(km/h)")
plt.ylabel("Visibility(km)")
plt.bar(windspeed,visibility)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
pressure=weather_df.iloc[:,10]
windspeed=weather_df.iloc[:,6]
plt.xlabel("Wind speed(km/h)")
plt.ylabel("Presssure(millibars))")
plt.bar(windspeed,pressure)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
windbearing=weather_df.iloc[:,7]
visibility=weather_df.iloc[:,8]
plt.xlabel("Wind bearing(degrees)")
plt.ylabel("Visibility(km/h)")
plt.bar(windbearing,visibility)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
windbearing=weather_df.iloc[:,7]
pressure=weather_df.iloc[:,10]
plt.xlabel("Wind bearing(degrees)")
plt.ylabel("Pressure(millibars)")
plt.bar(windbearing,pressure)
plt.show()
fig=plt.figure()
ax=fig.add_axes([0,0,1,1])
visibility=weather_df.iloc[:,8]
pressure=weather_df.iloc[:,10]
plt.ylabel("Pressure(millibars)")
plt.xlabel("Visibility(km/h)")
plt.bar(visibility,pressure)
plt.show()
#BARGRAPHS pictures Streamlit
st.title("BarGraphs Of WeatherData")
st.image("temp_vs_app_temperature.png")
st.image("temp_vs_humidity.png")
st.image("temp_vs_windspeed.png")
st.image("temp_vs_windbearing.png")
st.image("temp_vs_visibility.png")
st.image("app_temp_vs_humidity.png")
st.image("app_temp_vs_wind_speed.png")
st.image("app_temp_vs_wind_bearing.png")
st.image("app_temp_vs_visibility.png")
st.image("app_temp_vs_pressure.png")
st.image("humidity_vs_windspeed.png")
st.image("humidity_vs_windbearing.png")
st.image("humidity_vs_visibilityh.png")
st.image("humidity_vs_pressure.png")
st.image("sped_vs_bearing.png")
st.image("windspeed_vs_visibility.png")
st.image("windspeed_vs_pressure.png")
st.image("bearing_vs_visibility.png")
st.image("bearing_vs_pressure.png")
st.image("visibility_vs_pressure.png")


