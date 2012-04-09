# Emailer  

This plugin provides a simple emailer.

## installation
* add ```"com.typesafe" % "play-plugins-mailer" % "2.0"``` to your dependencies (```project/Build.scala```)
* add ```com.typesafe.plugin.CommonsMailerPlugin``` to your ```conf/play.plugins```

furthermore, the following parameters can be configured in ```conf/application.conf```

```
smtp.host (mandatory)
smtp.port (defaults to 25)
smtp.ssl (defaults to no)
smtp.user (optional)
smtp.password (optional)
```


## using it from java 

```java
import com.typesafe.plugin.*;
MailerPlugin mail = play.api.Play.unsafeApplication().plugin(MailerPlugin.class);
mail.setSubject("mailer");
mail.addRecipient("my@email.com","toaddress");
mail.addFrom("Peter Hausel <noreply@email.com>");
//sends html and text, text can be empty
mail.send( "", "<html>html</html>" );
//sends ```text/text```
mail.send( "text" );

```

## using it from scala

```scala
import com.typesafe.plugin._
val mail = use[MailerPlugin].email
mail.setSubject("mailer")
mail.addRecipient("my@email.com","toaddress")
mail.addFrom("Peter Hausel <noreply@email.com>")
//sends html and text, text can be empty
mail.send( "", "<html>html</html>" )
//sends ```text/text```
mail.send( "text" )

```


## Licence

This software is licensed under the Apache 2 license, quoted below.

Copyright 2012 Typesafe (http://www.typesafe.com).

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this project except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.