# Deleting an Object Using the AWS SDK for Ruby<a name="DeletingOneObjectUsingRubySDK"></a>

The following tasks guide you through using the Ruby classes to delete an object in Amazon S3.

The following Ruby example deletes an object from a bucket\. Because this example shows how to delete objects from non\-versioned buckets, it provides only the bucket name and object key \(not a version ID\) in the delete request\. \. 

```
require 'aws-sdk-s3'

bucket_name = '*** Provide bucket name ***'
key_name = '*** Provide key ***'

begin
 s3 = Aws::S3::Client.new(region: 'us-west-2')
 // Delete an object from the bucket.
 s3.deleteObject({:bucket => bucket_name, :key => key_name})
rescue Exception => ex
  puts 'Caught exception deleting object ' +  key_name + ' from bucket ' + bucket_name + ':'
  puts ex.message
end

puts 'Deleted ' + key_name + ' from bucket ' + bucket_name 

```
