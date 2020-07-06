# ExoticInstrumentAllOf

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**content** | **str** | The original document received into the system. This format could potentially be anything though is most likely to be either Json or Xml. In the case where no other              interface is supported it is possible to fall back onto this.              For example, a trade from an external client system. This may be recognized internally by Lusid or simply passed through to another vendor system. | 
**instrument_format** | [**InstrumentDefinitionFormat**](InstrumentDefinitionFormat.md) |  | 
**instrument_type** | **str** | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Exotic, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedRateLeg, FloatingRateLeg, BespokeCashflowLeg, Unknown | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

