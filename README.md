# IOPP-code-
IOPP lab assessment

 Develop an application to manage Dept Seminar Hall

Solution:

package seminarhall;
import java.io.FileNotFoundException;
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
import java.util.Date;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.geometry.Insets;
import javafx.geometry.Pos;
import javafx.scene.control.Alert;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.control.PasswordField;
import javafx.scene.control.DatePicker;
import javafx.scene.control.RadioButton;
import javafx.scene.control.ToggleButton;
import javafx.scene.control.ToggleGroup;
import javafx.scene.layout.GridPane;
import javafx.scene.text.Font;
import javafx.scene.text.FontPosture;
import javafx.scene.text.FontWeight;
import javafx.stage.Stage;
/**
*
* @author pooja
*/
public class Seminarhall extends Application {
 Label response;

	
TextField txtusrname;
 TextField txtDeptName;
 TextField txtActivityName;
 TextField txtDays;
 TextField txtStudentid;
 DatePicker StartDatedtpckr;
 DatePicker EndDatedtpckr ;
 ToggleGroup tgAvailability,tgGender;
 PasswordField txtpwd;
 DatePicker dtpckr;
 RadioButton rdmale,rdfemale;
 Scene snResult;
 Label resulttheader;
 TextField txtname;
 GridPane resultpane;
 Label lbllocdatetetxt;
 RadioButton rb;
 Label lbltxgender;
 Label lblgender;
 String BookDate="2021-12-13";
 String BookDate2="2021-12-14";
 String BookStartTime="2pm";
 String BookEndTime="3pm";
 String[] Data=new String[8];
 int count=0;
 
 
 @Override
 public void start(Stage stage) throws FileNotFoundException {
 try{
 Label lblheading=new Label("login page");
 Label lblusrname=new Label("User Name");
 Label lblpwd=new Label("Password");
 
 txtusrname=new TextField();
 
 txtpwd=new PasswordField();
 lblgender=new Label("gender");
 ToggleGroup tgGender=new ToggleGroup();
 rdmale=new RadioButton("Male");
 rdmale.setToggleGroup(tgGender);
 rdfemale=new RadioButton("Female");	

rdfemale.setToggleGroup(tgGender);
 
 Button btnSubmit=new Button("Submit");
 Button btnClear=new Button("Clear");
 
 GridPane gp_login=new GridPane();
 
 gp_login.setMinSize(400,200);
 
 gp_login.setPadding(new Insets(10,10,10,10));
 
 gp_login.setVgap(5);
 gp_login.setHgap(5);
 
 gp_login.setAlignment(Pos.CENTER);
 
 gp_login.add(lblheading,0,0,3,1);
 gp_login.add(lblusrname,0,1);
 gp_login.add(txtusrname,1,1);
 gp_login.add(lblpwd,0,2);
 gp_login.add(txtpwd,1,2);
 gp_login.add(lblgender,0,3);
 gp_login.add(rdmale,1,3);
 gp_login.add(rdfemale,3,3);
 gp_login.add(btnSubmit,1,4);
 gp_login.add(btnClear,2,4);
 
 //Scene-2
 Label lblheading1=new Label("seminar hall");
 Label lblDeptName=new Label("DeptName");
 
 txtDeptName=new TextField();
 
 Label lblActivityName=new Label("Activity Name");
 txtActivityName=new TextField();
 
 Label lblDays=new Label("Days");
 txtDays=new TextField(); 
 
 Label lblStartDate=new Label("StartDate");
 StartDatedtpckr=new DatePicker();
 
 Label lblEndDate=new Label("EndDate");
 EndDatedtpckr=new DatePicker();

Label lblStartTime=new Label("StartTime");
 TextField txtStartTime=new TextField();
 
 Label lblEndTime=new Label("EndTime");
 TextField txtEndTime=new TextField();
 
 Label AvailableResult=new Label("seminar hall is not available");
 Label AvailableResult2=new Label("seminar hall is available");
 
 
 ToggleButton tbAvailability=new ToggleButton();
 ToggleButton tbyes=new ToggleButton("Availability");
 
 ToggleButton tg_Availability=new ToggleButton();
 
 tbyes.setToggleGroup(tgAvailability);
 
 Label lblbooking=new Label("Booking seminar hall");
 
 
 Button btnBooking=new Button("Book");
 Button btnAuthentication=new Button("authenticate");
 Button btnFacility=new Button("Facility");
 
 GridPane gridPane=new GridPane();
 
 gridPane.setMinSize(500,500);
 
 gridPane.setPadding(new Insets(10,10,10,10));
 
 gridPane.setVgap(5);
 gridPane.setHgap(5);
 
 gridPane.setAlignment(Pos.CENTER);
 
 gridPane.add(lblheading1,0,0,3,1);
 gridPane.add(lblDeptName,0,1);
 gridPane.add(txtDeptName,1,1);
 
 gridPane.add(lblActivityName,0,2);
 gridPane.add(txtActivityName,1,2);
 gridPane.add(lblDays,0,3);
 gridPane.add(txtDays,1,3);

gridPane.add(lblStartDate,0,4);
 
 gridPane.add(StartDatedtpckr,1,4);
 
 gridPane.add(lblEndDate,0,5);
 gridPane.add(EndDatedtpckr,1,5);
 
 gridPane.add(lblStartTime,0,6);
 gridPane.add(txtStartTime,1,6);
 gridPane.add(lblEndTime,0,7);
 gridPane.add(txtEndTime,1,7);
 gridPane.add(tbyes,1,8);
 
 gridPane.add(lblbooking,0,9);
 gridPane.add(btnBooking,1,9);
 
 gridPane.add(btnAuthentication,0,14);
 gridPane.add(btnFacility,0,15);
 //scene3
 Label lblheading2=new Label("Authentication and Facility Screen");
 
 GridPane gp_unquie=new GridPane();
 gp_unquie.setMinSize(500,500);
 
 gp_unquie.setPadding(new Insets(10,10,10,10));
 
 gp_unquie.setVgap(5);
 gp_unquie.setHgap(5);
 
 gp_unquie.setAlignment(Pos.CENTER);
 gp_unquie.add(lblheading2,0,0,3,1);
 
 Label lblStudentid=new Label("Enter Student id");
 
 txtStudentid=new TextField();
 
 gp_unquie.add(lblStudentid,0,1);
 gp_unquie.add(txtStudentid,1,1);
 
 Button btnSubmitAuth=new Button("SubmitAuthentication");
 gp_unquie.add(btnSubmitAuth,0,2);

Scene scene=new Scene(gp_login);
Scene sc2=new Scene(gridPane);
Scene sc3=new Scene(gp_unquie);
btnSubmit.setOnAction((ActionEvent event) -> {
 
 
if((txtusrname.getText().equalsIgnoreCase("Pooja")&&txtpwd.getText().equalsI
gnoreCase("19cs072"))){
 stage.setScene(sc2);
 stage.setMaximized(true);
 }
 else{
 Alert alMsg=new Alert(Alert.AlertType.INFORMATION);
 alMsg.setContentText("Invalid User name or Password!!!!");
 alMsg.setTitle("Login Alert Window");
 alMsg.show();
 }
 
});
tbyes.setOnAction(new EventHandler<ActionEvent>() {
 @Override
 public void handle(ActionEvent event) {
 LocalDate StartDate=StartDatedtpckr.getValue();
 String formattedStartDate = 
StartDate.format(DateTimeFormatter.ISO_DATE);
 LocalDate EndDate=EndDatedtpckr.getValue();
 String formattedEndDate = 
EndDate.format(DateTimeFormatter.ISO_DATE);
 String formattedStartTime=txtStartTime.getText().toString();
 String formattedEndTime=txtEndTime.getText().toString();
 
if(formattedStartDate.equals(BookDate)&&formattedEndDate.equals(BookDa2)
 &&formattedStartTime.equals(BookStartTime) 
&&formattedEndTime.equals(BookEndTime) ){
 System.out.println("hi");
 gridPane.add(AvailableResult,0,11);
 gridPane.clearConstraints(AvailableResult2);
 } else {
 System.out.println("StartDate" + StartDatedtpckr.getValue());
 System.out.println("BookDate" + BookDate);
 gridPane.add(AvailableResult2,0,10);
 gridPane.clearConstraints(AvailableResult);
 }

}
 
 
});
 btnBooking.setOnAction(new EventHandler<ActionEvent>() {
 @Override
 public void handle(ActionEvent event) {
 
 
 
 String Result1="seminar hall is not available";
 String Result2="seminar hall is available";
 
 Label Result3=new Label("seminar hall is not booked");
 Label Result4=new Label("seminar hall is booked");
 
 LocalDate StartDate=StartDatedtpckr.getValue();
 String formattedStartDate = 
StartDate.format(DateTimeFormatter.ISO_DATE);
 LocalDate EndDate=EndDatedtpckr.getValue();
 String formattedEndDate = 
EndDate.format(DateTimeFormatter.ISO_DATE);
 String formattedStartTime=txtStartTime.getText().toString();
 String formattedEndTime=txtEndTime.getText().toString();
 
if(formattedStartDate.equals(BookDate)&&formattedEndDate.equals(BookDate2)
 &&formattedStartTime.equals(BookStartTime) 
&&formattedEndTime.equals(BookEndTime) ){
 System.out.println("hi");
 gridPane.add(Result3,0,13);
 gridPane.clearConstraints(Result4);
 gridPane.clearConstraints(AvailableResult2);
 gridPane.clearConstraints(AvailableResult);
 } else {
 System.out.println("StartDate" + StartDatedtpckr.getValue());
 System.out.println("BookDate" + BookDate);
 gridPane.add(Result4,0,12);
 gridPane.clearConstraints(Result3);
 gridPane.clearConstraints(AvailableResult);
 gridPane.clearConstraints(AvailableResult2);
 }
}
 
 
 }); 
 btnAuthentication.setOnAction(new EventHandler<ActionEvent>(){
 @Override
 public void handle(ActionEvent event) {
 stage.setScene(sc3);
 stage.setMaximized(true);
 
 }
 
 });
 btnSubmitAuth.setOnAction(new EventHandler<ActionEvent>(){
 @Override
 public void handle(ActionEvent event) {
 
 Label AuthResult1=new Label("entered student is authorized");
 Label AuthResult2=new Label("entered student is not authorized");
 if((txtStudentid.getText().equalsIgnoreCase("1234"))){
 
 gp_unquie.clearConstraints(AuthResult2);
 gp_unquie.add(AuthResult1,0,3);
 
 }
 else{
 
 gp_unquie.clearConstraints(AuthResult1);
 gp_unquie.add(AuthResult2,0,4);
 }
 
 }
 
 });
 btnFacility.setOnAction(new EventHandler<ActionEvent>(){
 @Override
 public void handle(ActionEvent event) {
 stage.setScene(sc3);
 stage.setMaximized(true);
 Label Facility1=new Label("Projector");
 Label Facility2=new Label("Mike");
 Label Facility3=new Label("AC");
 gp_unquie.add(Facility1,0,5);

gp_unquie.add(Facility2,0,6);
 gp_unquie.add(Facility3,0,7);
 
 }
 
 });
 
 btnClear.setOnAction(new EventHandler<ActionEvent>() {
 @Override
 public void handle(ActionEvent event) {
 txtusrname.clear();
 txtpwd.clear();
 
 }
 });
 stage.setScene(scene);
 stage.setMaximized(true);
 stage.show();
 
 
 
 
 
 
 }catch(Exception e){
 
 }
 
 }
 public static void main(String[] args) {
 launch(args);
 }
}
