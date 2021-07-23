<!DOCTYPE html>
<html>
<head>
<link href="https://fonts.googleapis.com/css?family=Megrim" rel="stylesheet" type="text/css">

<style>
 #typing-text {
     color: #FFFFFF;
     border: dashed 3px #FFFFFF;
     font-weight: bold;
     text-align: left;
     font-family: Megrim;
     overflow: auto;
     background-color: #380026;
     font-size: 40px;
     padding: 20px;
     height: 103px;
     width: 524px;
     outline: none;
     resize: none;
     box-sizing: border-box;
}

</style>
</head>
<body>
<textarea id="typing-text" readonly></textarea>


<script>
(function () {
   var CharacterPos = 0;
   var MsgBuffer = "";
   var TypeDelay = 100; 
   var NxtMsgDelay = 1000;
   var MsgIndex = 0;
   var delay;
   var MsgArray = ["Hi I am Tushar Amdoskar"];

   function StartTyping() {
      var id = document.getElementById("typing-text");
      if (CharacterPos != MsgArray[MsgIndex].length) {
         MsgBuffer  = MsgBuffer + MsgArray[MsgIndex].charAt(CharacterPos);
         id.value = MsgBuffer+"_";
         delay = TypeDelay;
         id.scrollTop = id.scrollHeight; 
      } else {
         delay = NxtMsgDelay;
         MsgBuffer   = "";
         CharacterPos = -1;
         if (MsgIndex!=MsgArray.length-1){
           MsgIndex++;
         }else {
           MsgIndex = 0;
         }
       }
       CharacterPos++;
       setTimeout(StartTyping,delay);
   }
StartTyping();
})();
</script>

</body>
</html>
