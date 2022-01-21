# other

<?php

$mobile  = is_numeric(strpos(strtolower($_SERVER['HTTP_USER_AGENT']),"mobile"));
$android = is_numeric(strpos(strtolower($_SERVER['HTTP_USER_AGENT']),"android"));

$token   = bin2hex(random_bytes(16)); #generates a crypto-secure 32 characters long 

if($mobile==1 OR $android==1)
{
    echo 'You are using a mobile device';
    #DB::table('user')->where(['email'=>$request->email])->update(['mobile_token'=>$token]);
}
else
{
    echo 'You are using a browser';
    #DB::table('user')->where(['email'=>$request->email])->update(['browser_token'=>$token]);
}


?>
