# IBM::EC2::Alarm

This resource type represents an alarm on Amazon Elastic Compute Cloud. It extends the type OS::Ceilometer::Alarm.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|alarm\_actions|List|False|Core|A list of URLs to invoke when the state makes the transition to `alarm`.|
|comparison\_operator|String|False|Core|Operator that is used to compare specified statistic with threshold. The following values are allowed:-   `ge`
-   `gt`
-   `eq`
-   `ne`
-   `lt`
-   `le`

|
|description|String|False|Core|Description for the alarm.|
|enabled|Boolean|False|Core|True if alarm evaluation and actions are enabled. By default, the enabled parameter is set to `True`.|
|evaluation\_periods|Integer|False|Core|Number of periods to evaluate over.|
|insufficient\_data\_actions|List|False|Core|A list of URLs to invoke when the state makes the transition to `insufficient-data`.|
|matching\_metadata|Map|False|Core|In addition to the meter name, the meter must match this resource metadata \(key=value\).|
|meter\_name|String|True|Core|Meter name that is watched by the alarm.|
|name|String|False|Core|Name of alarm.|
|ok\_actions|List|False|Core|A list of URLs to invoke when state makes the transition to `OK`.|
|period|Integer|False|Core|Period to evaluate over, in seconds.|
|repeat\_actions|Boolean|True|Core|Set the repeat\_actions parameter to `False` to trigger actions when the threshold is reached and the alarm's state has changed. By default, actions are called each time that the threshold is reached.|
|statistic|String|False|Core|Meter statistic to evaluate. The following values are allowed:-   `count`
-   `avg`
-   `sum`
-   `min`
-   `max`

|
|threshold|Number|True|Core|Threshold to evaluate against.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

