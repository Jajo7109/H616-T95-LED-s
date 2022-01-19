# H616-T95-LED-s
any information presented here is for educational purposes only. Opening the device and its modifications will void the warranty. You perform all activities at your own risk, I am not responsible for any damages.

If you have never had a soldering iron in your hand, start with something simpler. You will save yourself nerves and money.

TV BOX board H616 - T95MAX - V4.0 has been equipped with the option of adding two LEDs.
The diodes are driven from port "H" bits 6 and 7.
Depending on the connection, they can be active in the low or high state.
See attached picture 'T95_leds.jpg'.
Your DTS file must contain a declaration:

	leds {
		compatible = "gpio-leds";

		led-0 {
			function = LED_FUNCTION_POWER;
			color = <LED_COLOR_ID_RED>;
			gpios = <&pio 7 6 GPIO_ACTIVE_HIGH>; /* PH6 */
			default-state = "on";
		};

		led-1 {
			function = LED_FUNCTION_STATUS;
			color = <LED_COLOR_ID_GREEN>;
			gpios = <&pio 7 7 GPIO_ACTIVE_HIGH>; /* PH7 */
		};
	};
