
/***********************************************************************
*                                                                      *
* OnbotJava Editor is still : beta! Please inform us of any bugs       |
* on our discord channel! https://discord.gg/e7nVjMM                   *
* Only BLOCKS code is submitted when in Arena                          *
*                                                                      *
***********************************************************************/


public class MyFIRSTJavaOpMode extends LinearOpMode {
    DcMotor backLeftDrive;
    DcMotor backRightDrive;
    DcMotor frontLeftDrive;
    DcMotor frontRightDrive;
    

@Override
    public void runOpMode() {
      backLeftDrive = hardwareMap.get(DcMotor.class, "backLeftDrive");
      backRightDrive = hardwareMap.get(DcMotor.class, "backRightDrive");
      frontLeftDrive = hardwareMap.get(DcMotor.class, "frontLeftDrive");
      frontRightDrive = hardwareMap.get(DcMotor.class, "frontRightDrive");
      
        backLeftDrive.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
        backRightDrive.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
        frontLeftDrive.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
        frontRightDrive.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
    
        backLeftDrive.setTargetPosition(1000);
        backRightDrive.setTargetPosition(1000);
        frontLeftDrive.setTargetPosition(1000);
        frontRightDrive.setTargetPosition(1000);
        
        backLeftDrive.setMode(DcMotor.RunMode.RUN_TO_POSITION);
        backRightDrive.setMode(DcMotor.RunMode.RUN_TO_POSITION);
        frontLeftDrive.setMode(DcMotor.RunMode.RUN_TO_POSITION);
        frontRightDrive.setMode(DcMotor.RunMode.RUN_TO_POSITION);
      // Put initialization blocks here
      waitForStart();
      // Put run blocks here
      while (opModeIsActive() && backLeftDrive.isBusy() && backRightDrive.isBusy() && frontLeftDrive.isBusy() && frontRightDrive.isBusy()) {
      // Put loop blocks here
          telemetry.addData("encoder-back-left", backLeftDrive.getCurrentPosition());
          telemetry.addData("encoder-back-right", backRightDrive.getCurrentPosition());
          telemetry.addData("encoder-fwd-left", frontLeftDrive.getCurrentPosition());
          telemetry.addData("encoder-fwd-right", frontRightDrive.getCurrentPosition());
          
          telemetry.update();
          
          idle();

      }
        backLeftDrive.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
        backRightDrive.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
        frontLeftDrive.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
        frontRightDrive.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
    }
    
    
    
}
