# aadhaar
Python APIs to verify aadhaar number using Web Scraping on [Unique Identification Authority of India](https://uidai.gov.in/) GOI website.

Note: in code base, I used the word `adhar` instead of `aadhaar` for less typing.







To use Python API to verify a Aadhaar number:

![123](https://user-images.githubusercontent.com/8972586/54993544-1122a180-4fe8-11e9-9244-be952acf1931.png)


in case the CLI faces any issue : 
```
class AadhaarVerificationAPI:
    def __init__(self, aadhaar_number=None):
        self.adhar = aadhaar_number
        self.captcha_code = None
    
    def show_captcha(self):
        """ Simulates showing a CAPTCHA for user verification. """
        print("CAPTCHA: 0384")  # Simulated CAPTCHA
        return "0384"

    def verify(self):
        """ Simulates verification of Aadhaar details. """
        if not self.adhar:
            return {"error": "Aadhaar number is missing"}
        
        return {
            "Age Band": "30-40",
            "Gender": "MALE",
            "Mobile Number": "xxxxxxxx520",
            "State": "Delhi",
            "Aadhaar": self.adhar
        }

# ✅ Testing the API
webapi = AadhaarVerificationAPI("442837314297")
print(webapi.show_captcha())  # Should print "CAPTCHA: 0384"
webapi.captcha_code = "0384"  # User enters the CAPTCHA
print(webapi.verify())  # Should return Aadhaar details
```
