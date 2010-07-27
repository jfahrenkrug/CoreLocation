/*
 * Jakefile
 * CoreLocation
 *
 * Created by Johannes Fahrenkrug on July 27, 2010.
 * Copyright 2010, Springenwerk All rights reserved.
 */


 var FILE = require("file"),
     ENV  = require("system").env,
     Jake = require("jake"),
     task = Jake.task,
     FileList = Jake.FileList,
     bundle = require("objective-j/jake").bundle,
     framework = require("objective-j/jake").framework,
     environment = require("objective-j/jake/environment");

 $CONFIGURATION = ENV['CONFIG'] || "Release";

 $BUILD_DIR = ENV['CAPP_BUILD'] || ENV['STEAM_BUILD'];

 bundle ("CoreLocation", function(task)
 {
     task.setBuildIntermediatesPath(FILE.join($BUILD_DIR, "CoreLocation.build", $CONFIGURATION))
     task.setBuildPath(FILE.join($BUILD_DIR, $CONFIGURATION));

     task.setAuthor("Kelly Plummer, Johannes Fahrenkrug");
     task.setEmail("johannes @nospam@ springenwerk.com");
     task.setSummary("CoreLocation for Cappuccino");
     task.setIdentifier("com.springenwerk.CoreLocation");
     task.setSources(new FileList("*.j"), [environment.Browser, environment.CommonJS]);
     task.setResources([]);//All the resources belong to the plugin
     task.setFlattensSources(true);

     if ($CONFIGURATION === "Release")
         task.setCompilerFlags("-O");
     else
         task.setCompilerFlags("-DDEBUG -g");
 });

 task ("build", ["CoreLocation"]);
 task ("default", ["build"]);