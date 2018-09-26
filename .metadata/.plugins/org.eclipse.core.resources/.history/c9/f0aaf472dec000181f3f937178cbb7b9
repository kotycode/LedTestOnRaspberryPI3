package system.rspi.LedTestWithJavaHelp;

import com.pi4j.io.gpio.GpioController;
import com.pi4j.io.gpio.GpioFactory;
import com.pi4j.io.gpio.GpioPinDigitalOutput;
import com.pi4j.io.gpio.PinState;
import com.pi4j.io.gpio.RaspiPin;

public class LedControl {

	public static void main(String[] args) throws InterruptedException {

		// get GIPO controller
		final GpioController gpio = GpioFactory.getInstance();

		// create the pin with parameter PinState.HIGH
		// will instantly power up the pin
		final GpioPinDigitalOutput pin = gpio.provisionDigitalOutputPin(RaspiPin.GPIO_01,
				"PinLED", PinState.HIGH);
		System.out.println("Lights ON");
		
		// wait 2 sec
		Thread.sleep(2000);
		
		// turn off GPIO 1
		pin.low();
		System.out.println("End of light");
		
		// wait 1 sec
		Thread.sleep(1000);
		
		// turn on GPIO 1 and then turn off
		System.out.println("Light is on for 1 sec");
		pin.pulse(1000, true);
		
		// release the GPIO controller res
		gpio.shutdown();
		
	}
}
