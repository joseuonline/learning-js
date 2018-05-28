// Global variables initialized to null 
var image = null;
var grayImage = null;
var redhueImage=null;
var rainbowImage=null;
var blurImage=null;
var invertImage = null;
var contrastImage = null;
var redImage =null;
var greenImage =null;
var blueImage=null;
var borderImage=null;
var r=null;
var g=null;
var b=null;
var ResetImage = null;
var canvas=document.getElementById("canvas"); // Make the canvas a global variable

function uploadImage(){ // Uploads and displays an image to the canvas, creating copies of this image to be use in different functions
  var file=document.getElementById("imageInput");
  image= new SimpleImage(file); 
  // Create copies of the image in the following global variables
  ResetImage=new SimpleImage(file); 
  grayImage= new SimpleImage(file);
  redhueImage= new SimpleImage(file); 
  rainbowImage= new SimpleImage(file);
  blurImage= new SimpleImage(file);
  invertImage= new SimpleImage(file); 
  contrastImage= new SimpleImage(file); 
  redImage=new SimpleImage(file); 
  greenImage=new SimpleImage(file); 
  blueImage=new SimpleImage(file); 
  borderImage= new SimpleImage(file); 
  image.drawTo(canvas);
}

function imageIsLoaded(checkImage){ // Checks if the an image is loaded
  if (checkImage == null || !checkImage.complete()){
  alert ('The image has not been loaded');
  return false;
  } else {
  return true;
  }
}// End of function 

function makeGray() { // Changes the image to a gray scale version of itself
if (imageIsLoaded(grayImage)){
filterGray(grayImage);
grayImage.drawTo(canvas);
}
}

function filterGray (image){
// For loop to change each pixel of the image to a grayscale value while maintaining the brightness
for (var pixel of image.values()){
    // get the pixel's RGB values
    var red= pixel.getRed();
    var green= pixel.getGreen();
    var blue= pixel.getBlue();
    // Calculate the average value
    average= (red+green+blue)/3;
    // Assign this average vale to the pixel's RGB values
     pixel.setRed(average);
     pixel.setGreen(average);
     pixel.setBlue(average);
} // End of for loop 
}

function doRedHue(){
 // Check if the image has been loaded correctly 
if (imageIsLoaded(redhueImage)){
FilterRedHue(redhueImage);
redhueImage.drawTo(canvas);
} 
}

function FilterRedHue(image){
for (var pixel of image.values()){
    // get the pixel's RGB values
    var red= pixel.getRed();
    var green= pixel.getGreen();
    var blue= pixel.getBlue();
    // Calculate the RGB average 
    average= (red+green+blue)/3;
    if (average<128){
        pixel.setRed(2*average);
        pixel.setGreen(0);
        pixel.setBlue(0);
        } else {
        pixel.setRed(255);
        pixel.setGreen((2*average)-255);
        pixel.setBlue((2*average)-255);
        }
} // End of for loop 
}

function rainbow (){ // Adds a rainbow filter to an image
// Check if the image has been loaded correctly 
if (imageIsLoaded(rainbowImage)){
addstripes(rainbowImage);
rainbowImage.drawTo(canvas);
} 
}

function addstripes (image) { //creates color stripes
// Obtain height of image 
var height= image.getHeight ();  
for (var pixel of image.values()){
// get the pixel's RGB values
var red= pixel.getRed();
var green= pixel.getGreen();
var blue= pixel.getBlue();
// Calculate the RGB average 
average= (red+green+blue)/3;
// Get the y value of pixel
var y= pixel.getY();
// Red Filter
if (y<height/7 && average<128){
 pixel.setRed(2*average);
 pixel.setGreen(0);
 pixel.setBlue(0);
 } 
 if (y<height/7 && average>=128){
 pixel.setRed(255);
 pixel.setGreen((2*average)-255);
 pixel.setBlue((2*average)-255);
 }
//Orange Filter
if (y>=height/7 && y<(2*height)/7 && average<128){
 pixel.setRed(2*average);
 pixel.setGreen(0.8*average);
 pixel.setBlue(0);
 } 
 if (y>=height/7 && y<(2*height)/7  && average>=128){
 pixel.setRed(255);
 pixel.setGreen((1.2*average)-51);
 pixel.setBlue((2*average)-255);
 }
//Yellow Filter
if (y>=(2*height)/7 && y<(3*height)/7 && average<128){
 pixel.setRed(2*average);
 pixel.setGreen(2*average);
 pixel.setBlue(0);
 } 
 if (y>=(2*height)/7 && y<(3*height)/7 && average>=128){
 pixel.setRed(255);
 pixel.setGreen(255);
 pixel.setBlue((2*average)-255);
 }
//Green Filter
if (y>=(3*height)/7 && y<(4*height)/7  && average<128){
 pixel.setRed(0);
 pixel.setGreen(2*average);
 pixel.setBlue(0);
 } 
 if (y>=(3*height)/7 && y<(4*height)/7 && average>=128){
 pixel.setRed((2*average)-255);
 pixel.setGreen(255);
 pixel.setBlue((2*average)-255);
 }
//Blue Filter
if (y>=(4*height)/7 && y<(5*height)/7 && average<128){
 pixel.setRed(0);
 pixel.setGreen(0);
 pixel.setBlue(2*average);
 } 
 if (y>=(4*height)/7 && y<(5*height)/7 && average>=128){
 pixel.setRed((2*average)-255);
 pixel.setGreen((2*average)-255);
 pixel.setBlue(255);
 }
//Indigo Filter
if (y>=(5*height)/7 && y<(6*height)/7 && average<128){
 pixel.setRed(0.8*average);
 pixel.setGreen(0);
 pixel.setBlue(2*average);
 } 
 if (y>=(5*height)/7 && y<(6*height)/7 && average>=128){
 pixel.setRed((1.2*average)-51);
 pixel.setGreen((2*average)-255);
 pixel.setBlue(255);
 }
//Violet Filter
if (y>=(6*height)/7 && y<=height && average<128){
 pixel.setRed(1.6*average);
 pixel.setGreen(0);
 pixel.setBlue(1.6*average);
 } 
 if (y>=(6*height)/7 && y<=height && average>=128){
 pixel.setRed((0.4*average)+153);
 pixel.setGreen((2*average)-255);
 pixel.setBlue((0.4*average)+153);
 }
}// End of internal for
}// End of loop

// BLUR FILTER
function doBlur(){ // Adds a blur filter to an image
// Check if the image has been loaded correctly 
if (imageIsLoaded(blurImage)){
var filteredImage= FilterBlur(blurImage);
filteredImage.drawTo(canvas);
} 
}

function FilterBlur (inputImage){
// Create an output image
var outputImage = new SimpleImage(inputImage.getWidth(),inputImage.getHeight()); // Empty image
var w = image.getWidth();
var h = image.getHeight();
// For loop to create the Blur Image
for (var pixel of inputImage.values()){
var x= pixel.getX(); // Get x coordinate for the pixel
var y= pixel.getY(); // Get y coordinate for the pixel
var ran=Math.random(); //Generate a random number between 0 and 1
if (ran>0.5){ //Half the time, we will copy the pixel from the original image to the output image
outputImage.setPixel (x,y,pixel);
}
if (ran<=0.5){ //The other half of the time we will find a pixel nearby and copy that pixel instead
// Get random coordinates of a nearby pixel 
var coordinates = nearbyPixelPosition();
var newX = coordinates[0];
var newY = coordinates[1];
  if (x+newX < w/5){
    XnearbyPixel = x+newX;
  } else {
    XnearbyPixel = x-newX;
  }
  if(y+newY < h/5){
    YnearbyPixel = y+newY;
  }else {
    YnearbyPixel = y-newY;
  }
// Copy this nearby pixel to the output image in x and y cordinates 
var nearbyPixel= inputImage.getPixel(XnearbyPixel,YnearbyPixel);
outputImage.setPixel (x,y,nearbyPixel);  
} // End of if (ran<=0.5)
}// Enf of for loop  
return outputImage;
}

function  nearbyPixelPosition (){
var qt=(Math.random())*10; //Generate a random number between 0 and 1   
var coordinateX= Math.round(qt);// Round the number to the nearest integer
var qt1=(Math.random())*10; //Generate a random number between 0 and 1
var coordinateY=Math.round(qt1);// Round the number to the nearest integer
return [coordinateX, coordinateY];
} 

function invert (){ // Inverts the RGB values of an image's pixels
  // Check if the image has been loaded correctly 
if (imageIsLoaded(invertImage)){
FilterInvert (invertImage);
invertImage.drawTo(canvas);
}
}

function FilterInvert (image) {
  for (var pixel of image.values()){
    // get the pixel's RGB values
    var red= pixel.getRed();
    var green= pixel.getGreen();
    var blue= pixel.getBlue();
    // Invert the values
    var newRed = 255-red;
    var newGreen = 255-green;
    var newBlue = 255-blue;
    // Assign the new values to the pixel's RGB values
     pixel.setRed(newRed);
     pixel.setGreen(newGreen);
     pixel.setBlue(newBlue);
} // End of for loop
}

function contrast(){ // Applies certain degree of contrast to the image 
  // Check if the image has been loaded correctly 
if (imageIsLoaded(contrastImage)){
FilterContrast(contrastImage);
contrastImage.drawTo(canvas);
}
}

function FilterContrast(image){
  for (var pixel of image.values()){
    // get the pixel's RGB values
    var red= pixel.getRed();
    var green= pixel.getGreen();
    var blue= pixel.getBlue();
    // Change the values 
    var amount= 50;
    var newRed = ((((red / 255) - 0.5) * amount) + 0.5) *     255;
    var newGreen = ((((green / 255) - 0.5) * amount) +       0.5) * 255;
    var newBlue = ((((blue / 255) - 0.5) * amount) + 0.5)     * 255;
    // Assign the new values to the pixel's RGB values
     pixel.setRed(newRed);
     pixel.setGreen(newGreen);
     pixel.setBlue(newBlue);
} // End of for loop
}


function makeRed() {
var slider=document.getElementById("change_red");
var input= slider.value;
 // For loop to change the red values of each pixel, depending on the slider input
for (var pixel of redImage.values()){
     pixel.setRed(input);
} 
redImage.drawTo(canvas);
}


function makeGreen() {
var canvas=document.getElementById("canvas");
var slider=document.getElementById("change_green");
var input= slider.value;
 // For loop to change the green values of each pixel, depending on the slider input
for (var pixel of greenImage.values()){
     pixel.setGreen(input);
} 
greenImage.drawTo(canvas);
}

function makeBlue() {
 var slider=document.getElementById("change_blue");
 var input= slider.value;
 // For loop to change the blue values of each pixel, depending on the slider input
for (var pixel of blueImage.values()){
     pixel.setBlue(input);
} 
blueImage.drawTo(canvas);
}

function pickColor(){
  // Check if the image has been loaded correctly 
if (imageIsLoaded(borderImage)){
HexToRGB();
} 
}

function HexToRGB(){ // function that converts hexadecimal values to RGB values 
var element= document.getElementById("clr");
var input= element.value;
r = parseInt(input.substring(1,3),16);
g = parseInt(input.substring(3,5),16);
b = parseInt(input.substring(5,7),16);
}

function addBorder (){ // function that adds border
 // Check if the image has been loaded correctly 
if (imageIsLoaded(borderImage)){
var BorderThickness= document.getElementById("thickness");
var input= BorderThickness.value;
createBorder(borderImage, input);
borderImage.drawTo(canvas);  
}
}
  
function createBorder (image, thickness) { // function that creates border
var width= image.getWidth ();    // Obtain width and height of image 
var height= image.getHeight ();  
for (var pixel of image.values()){
    var x= pixel.getX(); // Obtain x and y pixel's coordinates
    var y= pixel.getY();
    if (x<=thickness || x >=(width-thickness) || y<=thickness || y>= (height-thickness)){
    // Set pixel's RGB values to new values
    pixel.setRed(r);
    pixel.setGreen(g);
    pixel.setBlue(b);
    }// Enf of if statement 
}// End of for
}// End of function

function reset() {
 // Check if the image has been loaded correctly 
if (image == null || !image.complete()){
  alert ('The image has not been loaded');
} else {
//Reset all of the global variables for filter images to the original image. This way, if you run one of your filters after resetting, the filter will run on the original image, not on the already filtered image
    grayImage = new SimpleImage(image);
    redhueImage = new SimpleImage(image);
    rainbowImage= new SimpleImage(image);
    blurImage= new SimpleImage(image);
    invertImage = new SimpleImage(image);
    contrastImage =new SimpleImage(image);
    redImage = new SimpleImage(image);
    greenImage =new SimpleImage(image);
    blueImage=new SimpleImage(image);
    borderImage=new SimpleImage(image);
    r=null;
    g=null;
    b=null;
 // Draw ResetImage to Canvas
    ResetImage.drawTo(canvas);
}
}

function clearCanvas(){
// Find the canvas element in the HTML document
var canvas=document.getElementById("canvas");
// Get the canvases's context 
var context=canvas.getContext("2d");
// Clear the canvas
context.clearRect(0,0, canvas.width,canvas.height); 
// Initialize global variables to null 
image = null;
ResetImage = null;
grayImage = null;
redhueImage = null;
rainbowImage= null;
blurImage= null;
invertImage = null;
contrastImage= null;
redImage = null;
greenImage = null;
blueImage=null;
borderImage=null;
r=null;
g=null;
b=null;
}
