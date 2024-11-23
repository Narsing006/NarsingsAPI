#%RAML 1.0
title: bank-syt-api
/getAccountDetailes:
  description: "To get account detailes of an customers"
  get:
    queryParameters:
      accountNumber:
        type: integer
        required: true
      accountHolderName:
        required: true
        type: string
        maxLength: 30
        minLength: 15
      Date of Birth:
        required: true
        type: date-only
      Address:
        required: true
        type: string
        maxLength: 50
      Age:
        type: integer
        required: true
    responses:
      200:
        body:
          application/json:
            example:
              {
                Name: "Beesetti Narsingarao",
                DOB: "2000-JUNE-06",
                Country: "INDIA",
                Age: "23"
              }             
/createAccount:
  description: "To create New Account for the Customers"
  post:
    queryParameters:
      Branch : string
      Name: string
      DOB: string
      Country: string
    body:
      application/json:
        example:
          {
            "Name" : "Narsingarao Beesetti",
            "DOB" : "06-JUNE-2000",
            "Category" : "BC-D",
            "Address": "Chowduvada(village),Indhiramma colony,K.kotapdu (mandal),Vishakapatanam (District),Andhra Prandesh,531034",
            "Country": "INDIA"  
          }
    responses:
      201:
        body:
          application/json:
            example:
              {
                "message" : "Account created successfully"
              }
  put:
    body:
      application/json:
        description: To update the required fileds for an user
        example:
          {
            Name: "Narsingarao Beesetti",
            DOB: "06-JUNE-2000",
            Branch: "K.Kotapadu",
            Category: "BC-D",
            Address: "Chowduvada (Village),Indhiramma colony, K.Kotapadu Mandal,Vishakapatanam (District),Andhra Pradesh,531034",
            Country: "INDIA"
          }
    responses:
      200:
        body:
          application/json:
            example:
              {
                Message: "Updated successfully"
              }
          
          
      
  
          
           


 
