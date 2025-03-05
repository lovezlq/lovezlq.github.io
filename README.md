$Mobile_DetectModel = new Mobile_DetectModel();
        $isWeChat =$Mobile_DetectModel->isWeChat();
        $isAndroidOS =$Mobile_DetectModel->isAndroidOS();
        if ($isWeChat && $isAndroidOS){
            header("Content-type:application/pdf");
            header("Content-Disposition:attachment;filename='downloaded.pdf'");
            exit();
        }
        //跳转真实链接
