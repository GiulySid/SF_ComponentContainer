({
    doInit : function(component, event, helper) {
        
        var action 	= 	component.get("c.getName");
        action.setParams({
            "mtdName"	: 	component.get("v.ComponentSx")
        });
        
        action.setCallback(this, function(response){
            
            var state = response.getState();
            if (state === "SUCCESS")  { 
                var result=response.getReturnValue();
                var ComponentName=response.getReturnValue().NomeComponent__c;
                var ParsedResult={};
                var param=[];
                param=result.Parametri__c.split(';');
                console.log("PARAM SX: "+JSON.stringify(param));
                var val=[];
                val=result.Valori__c.split(';');
                console.log("VAL SX: "+JSON.stringify(val));
                for(var i=0; i<param.length ;i++){
                    console.log('PARAM S '+i+': '+param[i]);
                    console.log('VAL S '+i+': '+val[i]);
                    ParsedResult[param[i]]=val[i];
                }
                console.log("ParsedResult SX: "+JSON.stringify(ParsedResult));
                $A.createComponent(
                    "c:"+ComponentName,ParsedResult
                    ,
                    function(newButton, status, errorMessage){
                        //Add the new button to the body array
                        if (status === "SUCCESS") {
                            console.log("SID SUCCESS SYN");
                            var BodyS = component.get("v.BodyS");
                            BodyS.push(newButton);
                            component.set("v.BodyS", BodyS);
                        }
                        else if (status === "INCOMPLETE") {
                            console.log("No response from server or client is offline.")
                            // Show offline error
                        }
                            else if (status === "ERROR") {
                                console.log("Error: " + errorMessage);
                                // Show error message
                            }
                    }
                );
            }
            else{
                console.log("ERRORE DYNAM SID SX");
            }
            
            
        });
        $A.enqueueAction(action);
        
       var action2 	= 	component.get("c.getName");
        action2.setParams({
            "mtdName"	: 	component.get("v.ComponentDx")
        });
        
        action2.setCallback(this, function(response){
            
            var state = response.getState();
            console.log('SID DX');
            if (state === "SUCCESS")  { 
                var result=response.getReturnValue();
                var ComponentName=response.getReturnValue().NomeComponent__c;
                var ParsedResult={};
                var param=[];
                param=result.Parametri__c.split(';');
                console.log("PARAM DX: "+JSON.stringify(param));
                var val=[];
                val=result.Valori__c.split(';');
                console.log("VAL DX: "+JSON.stringify(val));
                for(var i=0; i<param.length ;i++){
                    console.log('PARAM D '+i+': '+param[i]);
                    console.log('VAL D '+i+': '+val[i]);
                    ParsedResult[param[i]]=val[i];
                }
                console.log("ParsedResult DX: "+JSON.stringify(ParsedResult));
                $A.createComponent(
                    "c:"+ComponentName,ParsedResult
                    ,
                    function(newButton, status, errorMessage){
                        //Add the new button to the body array
                        if (status === "SUCCESS") {
                            console.log("SID SUCCESS DYN DX");
                            var BodyD = component.get("v.BodyD");
                            BodyD.push(newButton);
                            component.set("v.BodyD", BodyD);
                        }
                        else if (status === "INCOMPLETE") {
                            console.log("No response from server or client is offline.")
                            // Show offline error
                        }
                            else if (status === "ERROR") {
                                console.log("Error: " + errorMessage);
                                // Show error message
                            }
                    }
                );
            }
            else{
                console.log("ERRORE DYNAM SID DX");
            }
            
            
        });
        $A.enqueueAction(action2);
    }
})
