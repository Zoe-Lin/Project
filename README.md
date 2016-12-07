function Isclearuser()
	{
		if(isset($_GET['callback'])){
			$message=array('message'=>'success');			
			$callback = trim($_GET['callback']);
			$nowuser= ServerSreachApi();
                 $check=M('clearuser')->where(array('username'=>$nowuser['un']))->find();
                if($check||!empty($check)){
                        $message=array('message'=>"fail");
                        echo $callback.'('.json_encode($message).')';
                 }else{
                  echo $callback.'('.json_encode($message).')';
                 }

		}

	}
