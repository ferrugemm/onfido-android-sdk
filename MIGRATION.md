# Onfido Android SDK Migration Guide

## `2.0.0` -> `2.1.0`

### Deprecations
- Deprecated `withApplicant(Applicant applicant)` method. We now recommend that you create an Onfido applicant yourself on your backend and 
the `withApplicant(String id)` method should be called with the id of the created applicant.

## `1.0.0` -> `2.0.0`

### Breaking changes
- Removed `FlowStep.MESSAGE_FACE_VERIFICATION`, which is now automatically added before any face capture with the variant `FaceCaptureVariant.PHOTO`.
This way, any inclusion of this step in a custom flow should be removed

## `0.9.2` -> `1.0.0`

### Breaking changes

- Removed the `allowMetrics(boolean)` method from the `OnfidoConfig.Builder` object. Every call to this method should be deleted
- Removed the previously deprecated `FlowStep.MESSAGE_IDENTIFY_VERIFICATION` enum instance, as it was too specific for our generic flow intentions. 
Every previous inclusion of this object on a flow should be replaced by a custom `MessageScreenStep`