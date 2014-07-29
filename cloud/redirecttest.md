---
layout: cloud
title: Redirect tester
---

<script type="text/javascript" src="../js/yaml.js"></script>
<script language="javascript">
$( document ).ready(function() {
  YAML.fromURL("../redirects.yaml",function(data){
    var errors = YAML.getErrors();
    if (errors.length == 0) {
      console.log("Done! Took " + YAML.getProcessingTime() + " miliseconds. data.redirects.length=" + data.redirects.length );
      console.log(data);
      for(var redirect in data.redirects)
      {
        console.log("redirect.length=" + redirect.length);
        //document.write(redirect.from + "=" redirect.to)
      }
    } else {
      console.log(document.getElementById("out").innerHTML = errors.join("<br>"));
    }
  });
});
</script>