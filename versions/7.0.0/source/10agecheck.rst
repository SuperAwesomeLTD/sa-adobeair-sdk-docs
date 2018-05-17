Verifying a user's age
======================

A new feature in the SDK is the ability to verify a user's age, given a date of birth.

An example below:

.. code-block:: actionscript

  // a date of birth in YYYY-MM-DD format
  var dateOfBirth: String = "2012-02-02";

  AwesomeAds.triggerAgeCheck(dateOfBirth, function(model: GetIsMinorModel): void  => {
    if (model != null) {
      // relevant values in the model
      string country = model.country;
      int consentAge = model.consentAgeForCountry;
      int userAge = model.age;
      boolean isMinor = model.isMinor;
    }
  });
