# AWS::KinesisAnalytics::Application RecordFormat<a name="aws-properties-kinesisanalytics-application-recordformat"></a>

 Describes the record format and relevant mapping information that should be applied to schematize the records on the stream\. 

## Syntax<a name="aws-properties-kinesisanalytics-application-recordformat-syntax"></a>

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON<a name="aws-properties-kinesisanalytics-application-recordformat-syntax.json"></a>

```
{
  "[MappingParameters](#cfn-kinesisanalytics-application-recordformat-mappingparameters)" : [MappingParameters](aws-properties-kinesisanalytics-application-mappingparameters.md),
  "[RecordFormatType](#cfn-kinesisanalytics-application-recordformat-recordformattype)" : String
}
```

### YAML<a name="aws-properties-kinesisanalytics-application-recordformat-syntax.yaml"></a>

```
﻿  [MappingParameters](#cfn-kinesisanalytics-application-recordformat-mappingparameters) : 
    [MappingParameters](aws-properties-kinesisanalytics-application-mappingparameters.md)
﻿  [RecordFormatType](#cfn-kinesisanalytics-application-recordformat-recordformattype) : String
```

## Properties<a name="aws-properties-kinesisanalytics-application-recordformat-properties"></a>

`MappingParameters`  <a name="cfn-kinesisanalytics-application-recordformat-mappingparameters"></a>
When configuring application input at the time of creating or updating an application, provides additional mapping information specific to the record format \(such as JSON, CSV, or record fields delimited by some delimiter\) on the streaming source\.  
*Required*: No  
*Type*: [MappingParameters](aws-properties-kinesisanalytics-application-mappingparameters.md)  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`RecordFormatType`  <a name="cfn-kinesisanalytics-application-recordformat-recordformattype"></a>
The type of record format\.  
*Required*: Yes  
*Type*: String  
*Allowed Values*: `CSV | JSON`  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)