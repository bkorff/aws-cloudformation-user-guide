# AWS::CloudFront::Distribution CacheBehavior<a name="aws-properties-cloudfront-distribution-cachebehavior"></a>

A complex type that describes how CloudFront processes requests\.

You must create at least as many cache behaviors \(including the default cache behavior\) as you have origins if you want CloudFront to distribute objects from all of the origins\. Each cache behavior specifies the one origin from which you want CloudFront to get objects\. If you have two origins and only the default cache behavior, the default cache behavior will cause CloudFront to get objects from one of the origins, but the other origin is never used\.

For the current limit on the number of cache behaviors that you can add to a distribution, see [Amazon CloudFront Limits](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html#limits_cloudfront) in the *AWS General Reference*\.

If you don't want to specify any cache behaviors, include only an empty `CacheBehaviors` element\. Don't include an empty `CacheBehavior` element, or CloudFront returns a `MalformedXML` error\.

To delete all cache behaviors in an existing distribution, update the distribution configuration and include only an empty `CacheBehaviors` element\.

To add, change, or remove one or more cache behaviors, update the distribution configuration and specify all of the cache behaviors that you want to include in the updated distribution\.

For more information about cache behaviors, see [Cache Behaviors](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/distribution-web-values-specify.html#DownloadDistValuesCacheBehavior) in the *Amazon CloudFront Developer Guide*\.

## Syntax<a name="aws-properties-cloudfront-distribution-cachebehavior-syntax"></a>

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON<a name="aws-properties-cloudfront-distribution-cachebehavior-syntax.json"></a>

```
{
  "[AllowedMethods](#cfn-cloudfront-distribution-cachebehavior-allowedmethods)" : [ String, ... ],
  "[CachedMethods](#cfn-cloudfront-distribution-cachebehavior-cachedmethods)" : [ String, ... ],
  "[Compress](#cfn-cloudfront-distribution-cachebehavior-compress)" : Boolean,
  "[DefaultTTL](#cfn-cloudfront-distribution-cachebehavior-defaultttl)" : Double,
  "[FieldLevelEncryptionId](#cfn-cloudfront-distribution-cachebehavior-fieldlevelencryptionid)" : String,
  "[ForwardedValues](#cfn-cloudfront-distribution-cachebehavior-forwardedvalues)" : [ForwardedValues](aws-properties-cloudfront-distribution-forwardedvalues.md),
  "[LambdaFunctionAssociations](#cfn-cloudfront-distribution-cachebehavior-lambdafunctionassociations)" : [ [LambdaFunctionAssociation](aws-properties-cloudfront-distribution-lambdafunctionassociation.md), ... ],
  "[MaxTTL](#cfn-cloudfront-distribution-cachebehavior-maxttl)" : Double,
  "[MinTTL](#cfn-cloudfront-distribution-cachebehavior-minttl)" : Double,
  "[PathPattern](#cfn-cloudfront-distribution-cachebehavior-pathpattern)" : String,
  "[SmoothStreaming](#cfn-cloudfront-distribution-cachebehavior-smoothstreaming)" : Boolean,
  "[TargetOriginId](#cfn-cloudfront-distribution-cachebehavior-targetoriginid)" : String,
  "[TrustedSigners](#cfn-cloudfront-distribution-cachebehavior-trustedsigners)" : [ String, ... ],
  "[ViewerProtocolPolicy](#cfn-cloudfront-distribution-cachebehavior-viewerprotocolpolicy)" : String
}
```

### YAML<a name="aws-properties-cloudfront-distribution-cachebehavior-syntax.yaml"></a>

```
﻿  [AllowedMethods](#cfn-cloudfront-distribution-cachebehavior-allowedmethods) : 
    - String
﻿  [CachedMethods](#cfn-cloudfront-distribution-cachebehavior-cachedmethods) : 
    - String
﻿  [Compress](#cfn-cloudfront-distribution-cachebehavior-compress) : Boolean
﻿  [DefaultTTL](#cfn-cloudfront-distribution-cachebehavior-defaultttl) : Double
﻿  [FieldLevelEncryptionId](#cfn-cloudfront-distribution-cachebehavior-fieldlevelencryptionid) : String
﻿  [ForwardedValues](#cfn-cloudfront-distribution-cachebehavior-forwardedvalues) : 
    [ForwardedValues](aws-properties-cloudfront-distribution-forwardedvalues.md)
﻿  [LambdaFunctionAssociations](#cfn-cloudfront-distribution-cachebehavior-lambdafunctionassociations) : 
    - [LambdaFunctionAssociation](aws-properties-cloudfront-distribution-lambdafunctionassociation.md)
﻿  [MaxTTL](#cfn-cloudfront-distribution-cachebehavior-maxttl) : Double
﻿  [MinTTL](#cfn-cloudfront-distribution-cachebehavior-minttl) : Double
﻿  [PathPattern](#cfn-cloudfront-distribution-cachebehavior-pathpattern) : String
﻿  [SmoothStreaming](#cfn-cloudfront-distribution-cachebehavior-smoothstreaming) : Boolean
﻿  [TargetOriginId](#cfn-cloudfront-distribution-cachebehavior-targetoriginid) : String
﻿  [TrustedSigners](#cfn-cloudfront-distribution-cachebehavior-trustedsigners) : 
    - String
﻿  [ViewerProtocolPolicy](#cfn-cloudfront-distribution-cachebehavior-viewerprotocolpolicy) : String
```

## Properties<a name="aws-properties-cloudfront-distribution-cachebehavior-properties"></a>

`AllowedMethods`  <a name="cfn-cloudfront-distribution-cachebehavior-allowedmethods"></a>
A complex type that controls which HTTP methods CloudFront processes and forwards to your Amazon S3 bucket or your custom origin\. There are three choices:  
+ CloudFront forwards only `GET` and `HEAD` requests\.
+ CloudFront forwards only `GET`, `HEAD`, and `OPTIONS` requests\.
+ CloudFront forwards `GET, HEAD, OPTIONS, PUT, PATCH, POST`, and `DELETE` requests\.
If you pick the third choice, you may need to restrict access to your Amazon S3 bucket or to your custom origin so users can't perform operations that you don't want them to\. For example, you might not want users to have permissions to delete objects from your origin\.  
*Required*: No  
*Type*: List of String  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`CachedMethods`  <a name="cfn-cloudfront-distribution-cachebehavior-cachedmethods"></a>
A complex type that controls whether CloudFront caches the response to requests using the specified HTTP methods\. There are two choices:  
+ CloudFront caches responses to `GET` and `HEAD` requests\.
+ CloudFront caches responses to `GET`, `HEAD`, and `OPTIONS` requests\.
If you pick the second choice for your Amazon S3 Origin, you may need to forward Access\-Control\-Request\-Method, Access\-Control\-Request\-Headers, and Origin headers for the responses to be cached correctly\.   
*Required*: No  
*Type*: List of String  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`Compress`  <a name="cfn-cloudfront-distribution-cachebehavior-compress"></a>
Whether you want CloudFront to automatically compress certain files for this cache behavior\. If so, specify true; if not, specify false\. For more information, see [Serving Compressed Files](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/ServingCompressedFiles.html) in the *Amazon CloudFront Developer Guide*\.  
*Required*: No  
*Type*: Boolean  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`DefaultTTL`  <a name="cfn-cloudfront-distribution-cachebehavior-defaultttl"></a>
The default amount of time that you want objects to stay in CloudFront caches before CloudFront forwards another request to your origin to determine whether the object has been updated\. The value that you specify applies only when your origin does not add HTTP headers such as `Cache-Control max-age`, `Cache-Control s-maxage`, and `Expires` to objects\. For more information, see [Managing How Long Content Stays in an Edge Cache \(Expiration\)](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Expiration.html) in the *Amazon CloudFront Developer Guide*\.  
*Required*: No  
*Type*: Double  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`FieldLevelEncryptionId`  <a name="cfn-cloudfront-distribution-cachebehavior-fieldlevelencryptionid"></a>
The value of `ID` for the field\-level encryption configuration that you want CloudFront to use for encrypting specific fields of data for a cache behavior or for the default cache behavior in your distribution\.  
*Required*: No  
*Type*: String  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`ForwardedValues`  <a name="cfn-cloudfront-distribution-cachebehavior-forwardedvalues"></a>
A complex type that specifies how CloudFront handles query strings and cookies\.  
*Required*: Yes  
*Type*: [ForwardedValues](aws-properties-cloudfront-distribution-forwardedvalues.md)  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`LambdaFunctionAssociations`  <a name="cfn-cloudfront-distribution-cachebehavior-lambdafunctionassociations"></a>
A complex type that contains zero or more Lambda function associations for a cache behavior\.  
*Required*: No  
*Type*: List of [LambdaFunctionAssociation](aws-properties-cloudfront-distribution-lambdafunctionassociation.md)  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`MaxTTL`  <a name="cfn-cloudfront-distribution-cachebehavior-maxttl"></a>
The maximum amount of time that you want objects to stay in CloudFront caches before CloudFront forwards another request to your origin to determine whether the object has been updated\. The value that you specify applies only when your origin adds HTTP headers such as `Cache-Control max-age`, `Cache-Control s-maxage`, and `Expires` to objects\. For more information, see [Managing How Long Content Stays in an Edge Cache \(Expiration\)](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Expiration.html) in the *Amazon CloudFront Developer Guide*\.  
*Required*: No  
*Type*: Double  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`MinTTL`  <a name="cfn-cloudfront-distribution-cachebehavior-minttl"></a>
The minimum amount of time that you want objects to stay in CloudFront caches before CloudFront forwards another request to your origin to determine whether the object has been updated\. For more information, see [ Managing How Long Content Stays in an Edge Cache \(Expiration\)](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Expiration.html) in the * Amazon CloudFront Developer Guide*\.  
You must specify `0` for `MinTTL` if you configure CloudFront to forward all headers to your origin \(under `Headers`, if you specify `1` for `Quantity` and `*` for `Name`\)\.  
*Required*: No  
*Type*: Double  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`PathPattern`  <a name="cfn-cloudfront-distribution-cachebehavior-pathpattern"></a>
The pattern \(for example, `images/*.jpg`\) that specifies which requests to apply the behavior to\. When CloudFront receives a viewer request, the requested path is compared with path patterns in the order in which cache behaviors are listed in the distribution\.  
You can optionally include a slash \(`/`\) at the beginning of the path pattern\. For example, `/images/*.jpg`\. CloudFront behavior is the same with or without the leading `/`\.
The path pattern for the default cache behavior is `*` and cannot be changed\. If the request for an object does not match the path pattern for any cache behaviors, CloudFront applies the behavior in the default cache behavior\.  
For more information, see [Path Pattern](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/distribution-web-values-specify.html#DownloadDistValuesPathPattern) in the * Amazon CloudFront Developer Guide*\.  
*Required*: Yes  
*Type*: String  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`SmoothStreaming`  <a name="cfn-cloudfront-distribution-cachebehavior-smoothstreaming"></a>
Indicates whether you want to distribute media files in the Microsoft Smooth Streaming format using the origin that is associated with this cache behavior\. If so, specify `true`; if not, specify `false`\. If you specify `true` for `SmoothStreaming`, you can still distribute other content using this cache behavior if the content matches the value of `PathPattern`\.   
*Required*: No  
*Type*: Boolean  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`TargetOriginId`  <a name="cfn-cloudfront-distribution-cachebehavior-targetoriginid"></a>
The value of `ID` for the origin that you want CloudFront to route requests to when a request matches the path pattern either for a cache behavior or for the default cache behavior in your distribution\.  
*Required*: Yes  
*Type*: String  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`TrustedSigners`  <a name="cfn-cloudfront-distribution-cachebehavior-trustedsigners"></a>
A complex type that specifies the AWS accounts, if any, that you want to allow to create signed URLs for private content\.  
If you want to require signed URLs in requests for objects in the target origin that match the `PathPattern` for this cache behavior, specify `true` for `Enabled`, and specify the applicable values for `Quantity` and `Items`\. For more information, see [Serving Private Content through CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/PrivateContent.html) in the *Amazon CloudFront Developer Guide*\.   
If you don't want to require signed URLs in requests for objects that match `PathPattern`, specify `false` for `Enabled` and `0` for `Quantity`\. Omit `Items`\.  
To add, change, or remove one or more trusted signers, change `Enabled` to `true` \(if it's currently `false`\), change `Quantity` as applicable, and specify all of the trusted signers that you want to include in the updated distribution\.  
*Required*: No  
*Type*: List of String  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`ViewerProtocolPolicy`  <a name="cfn-cloudfront-distribution-cachebehavior-viewerprotocolpolicy"></a>
The protocol that viewers can use to access the files in the origin specified by `TargetOriginId` when a request matches the path pattern in `PathPattern`\. You can specify the following options:  
+  `allow-all`: Viewers can use HTTP or HTTPS\.
+  `redirect-to-https`: If a viewer submits an HTTP request, CloudFront returns an HTTP status code of 301 \(Moved Permanently\) to the viewer along with the HTTPS URL\. The viewer then resubmits the request using the new URL\. 
+  `https-only`: If a viewer sends an HTTP request, CloudFront returns an HTTP status code of 403 \(Forbidden\)\. 
For more information about requiring the HTTPS protocol, see [Using an HTTPS Connection to Access Your Objects](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/SecureConnections.html) in the *Amazon CloudFront Developer Guide*\.  
The only way to guarantee that viewers retrieve an object that was fetched from the origin using HTTPS is never to use any other protocol to fetch the object\. If you have recently changed from HTTP to HTTPS, we recommend that you clear your objects' cache because cached objects are protocol agnostic\. That means that an edge location will return an object from the cache regardless of whether the current request protocol matches the protocol used previously\. For more information, see [Managing How Long Content Stays in an Edge Cache \(Expiration\)](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Expiration.html) in the *Amazon CloudFront Developer Guide*\.
*Required*: Yes  
*Type*: String  
*Allowed Values*: `allow-all | https-only | redirect-to-https`  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

## See Also<a name="aws-properties-cloudfront-distribution-cachebehavior--seealso"></a>
+  [CacheBehavior](https://docs.aws.amazon.com/cloudfront/latest/APIReference/API_CacheBehavior.html) in the *Amazon CloudFront API Reference* 