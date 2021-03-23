cmake_minimum_required(VERSION 3.5)

set(srcs
 		"./src/FastLED.cpp"
		"./src/bitswap.cpp"
		"./src/colorpalettes.cpp"
		"./src/colorutils.cpp"
		"./src/hsv2rgb.cpp"
		"./src/lib8tion.cpp"
		"./src/noise.cpp"
		"./src/platforms.cpp"
		"./src/power_mgt.cpp"
		"./src/wiring.cpp"
# remove the following if you want I2S instead of RMT hardware, just put a pound in front
		"./src/platforms/esp/32/clockless_rmt_esp32.cpp"
		)


idf_component_register(SRCS "${srcs}"
			INCLUDE_DIRS "./src" 
            REQUIRES arduino)

target_compile_options(${COMPONENT_TARGET} PUBLIC "-DESP32")
