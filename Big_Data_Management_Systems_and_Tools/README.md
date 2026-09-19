**Group Project for Big Data Management Systems and Tools Course** \
*Author: Craig Vande Ligt*

**Topic:** Prediction of Class A Vessel Location from Automatic Information System Streamed Data \
**Objective:** To design a Big Data pipeline that ingests live AIS streamed data using Spark Structured Streaming, preprocess and clean the data, store it in a distributed format, and apply machine learning models to predict short-term Class A vessel movements, If time permits, the goal is to also apply the best model to the streamed data, mapping in near real-time the updated locations of these vessels. \
**Dataset:** \
Live AIS Vessel Data Feed (WebSocket API) \
https://aisstream.io \
\
API: wss://stream.aisstream.io/v0/stream \
Note: Data was collected using an incoming stream of data via Kafka over a one-hour period and stored as a parquet file. A downsampled dataset was then created of 500 Class A vessels to ensure adequate timelines for modelling and workflow development. \
**Summary:** 
- Built scalable end-to-end pipeline to predict Class A marine vessel locations from AIS stream data 
- Prototyped streaming ingestion options (including WebSocket to Kafka attempted, but found limitations), and implemented a stream-simulated architecture using Parquet storage and PySpark for distributed processing and feature generation
- Engineered vessel history/lag features and compared Random Forest, Gradient Boosted Trees, and Linear/Elastic-Net regression models for coordinate prediction; Linear/Elastic-Net was selected as the best performer, achieving strong geospatial prediction accuracy (low RMSE and distance-based error), and produced an interactive Leafmap visualization as proof-of-concept for live tracking and predicted next location display
