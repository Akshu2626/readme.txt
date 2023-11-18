# readme.txt
this is only for my remeber things only




//mongo url




URL="mongodb+srv://<username>:<password>@cluster0.vfuowqu.mongodb.net/<foldername>?retryWrites=true&w=majority"







//data dart to json 


import 'dart:convert';

import 'package:mongo_dart/mongo_dart.dart';

MongoDbModel mongoDbModelFromJson(String str) =>
    MongoDbModel.fromJson(json.decode(str));

String mongoDbModelToJson(MongoDbModel data) => json.encode(data.toJson());

class MongoDbModel {
  ObjectId id;
  String firstName;
  String lastName;
  String email;
  String jobProfile;
  String address;

  MongoDbModel({
    required this.id,
    required this.firstName,
    required this.lastName,
    required this.email,
    required this.jobProfile,
    required this.address,
  });

  factory MongoDbModel.fromJson(Map<String, dynamic> json) => MongoDbModel(
      id: json["id"],
      firstName: json["firstName"],
      lastName: json["lastName"],
      email: json["email"],
      jobProfile: json['jobprofile'],
      address: json["address"]);

  Map<String, dynamic> toJson() => {
        "id": id,
        "firstName": firstName,
        "lastName": lastName,
        "email": email,
        "jobProfile": jobProfile,
        "address": address,
      };
}





