# External Activation Platform 

As per the [documentation](https://help.salesforce.com/s/articleView?id=sf.c360_a_build_external_activation_platforms.htm&type=5), the External Activation Platform instructs Salesforce CDP on what data is required at the time of audience activation, how files should be formatted, and where they should be published when a Salesforce CDP customer activates an audience.  Once an admin installs your external activation platform and a marketer publishes segments, you'll start receiving segments to your Cloud File Storage (Amazon S3).

You'll receive three types of files per activation target per customer account: 
*  A metadata file containing details about fields you need to process the data correctly like the customer's account id in your system along with segment ids and segment names. 
* A group of files in a folder (named by the type of identifier selected) contain the hashed identifier along with segment ids for each segment the id is a member.
* A _SUCCESS file denotes that the files have been successfully published to the S3 bucket. 


Check out the [External Activation Platform Files in Cloud File Storage
](https://help.salesforce.com/s/articleView?id=sf.c360_a_package_external_activation_platform_find_metadata_reference.htm&type=5) document for more information about the file paths and structures. 


Here are some footnotes about the sample files contained in this folder:
* The [metadata.json](./metadata.json), [hashed-email-example.json](./hashed-email-example.json.gz), and [hashed-email-csv-example.json](./hashed-email-csv-example.csv.gz) files contain all segments published to an account. These sample files contain two segments. 
* The data files are delivered as a .gz file. You'll have to gunzip to be able to read the file. 
* There can be one or more partial data files per type per account. 
* The data files are currently only a full refresh. The "add" field is the segment membership. The remove field is reserved for future use.


## Resources
[External Activation Platform](https://help.salesforce.com/s/articleView?id=sf.c360_a_build_external_activation_platforms.htm&type=5)
[External Activation Platform Files in Cloud File Storage
](https://help.salesforce.com/s/articleView?id=sf.c360_a_package_external_activation_platform_find_metadata_reference.htm&type=5)