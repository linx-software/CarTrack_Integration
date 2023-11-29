# Cartrack Integration Sample

## Description
This repo contains a Linx 6 solution that shows how you can consume the [Cartrack API](https://cartrack.notion.site/REST-API-1e3c290c37844fdb9950729e52e68457). Use this solution as a base for your Cartrack integration. Add your system integration and uses the pre-created functions to interact with the Cartrack API. It makes use of a REST call to call the web service with a JSON body (handled by Types). The result is a JSON object that can be manipulated and consumed by other Linx functions or processes. The solution was made to be generic enough so that it will only call the endpoints and use them as you need to in your integration project.  

You can download this sample and manipulate it to suit your integration using [Linx 6](https://linx.software/).

## Installation
You will need the Linx 6 Designer, get it [here](https://linx.software/linx-download/)

The solution also makes use of two Settings that you will need to set: 

- CarTrackBaseURL: Set the base URL for the Cartrack API, this is preconfigured 

- CarTrackToken: Your CarTrack Token 

- CarTrackUser: Your CarTrack User 

## Usage

All [authentication details (Token and User)](https://cartrack.notion.site/Getting-Started-33bbc1e5bb654d358412410f59e7c86f#1b2633da8725450db66e3ddcea9b65f3) are placed in the settings.

The solution has 4 main functions:

#### CT_GetDrivers: 
This function will get all drivers. It works by calling the [drivers](https://cartrack.notion.site/Drivers-4b7568a33f3c474c9395cd9b7c2100f3) endpoint. It will return a list of drivers. 

#### CT_GetJobs:
This function will get a list of Jobs based on input dates. The function has two parameters:
- Created_From: This is the date that the order was create, and the filter will be applied on the API to filter only orders from the specified date. It is sent in the filter[ create_ts_from ] query parameter
- Created_To: This is the date that the order was create, and the filter will be applied on the API to filter only orders to the specified date. It is sent in the filter[ create_ts_to ] query parameter.

The date filter is applied between the two entered dates.

It works by calling the [jobs](https://cartrack.notion.site/Jobs-0fab16052fdf48e2a9d2a88180ce5976) endpoint. It will return a list of Jobs. 

#### CT_GetSpecificJob:
This function will get a specific job based on the JobID. The function has an input parameter for the JobID. It works by calling the [jobs](https://cartrack.notion.site/Jobs-0fab16052fdf48e2a9d2a88180ce5976) endpoint. 

#### CT_SaveNewJob:
This function will create a new Job. It has a type input parameter that will require you to input all delivery information, use the CarTrackDelivery type to know what fields are to be added. It works by calling the [jobs](https://cartrack.notion.site/Jobs-0fab16052fdf48e2a9d2a88180ce5976) POST endpoint. It will return a list of Jobs. 


## Contributing

For questions please ask the [Linx community](https://linx/software/community). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)
