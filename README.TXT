/* This driver edits add device attribute files which is the link from 
 * kernel space to user space. These files appear under 
 * /sys/devices/platform/ds2784-battery/ and are named age, voltAE,
 * setreg, dumpreg, statusreg, getvoltage and getcurrent. These files/
 * functions allow interaction with the battery's read and write functions
 * which is the foundation for a re-calibration mode app along with a number
 * of other features/advantages.
 * 
 */

/* setreg - creates a file called "setreg" and allows us to  
 * echo 2 values with a space between them, register and value, which
 * calls the battery write function.  For example, "echo 0x14 0x80" 
 * writes register 0x14 with a value of 0x80.
 * 
 */
 
 /* dumpreg - creates a file called "dumpreg" and this is a read-only
 * file.  When this file is read, it returns all values from the battery  
 * EEPROM chip. 
 */
 
 /* statusreg - creates a file called "statusreg" which is needed.
 * This allows us to read the status register more frequently than
 * the driver's 1-minute intervals. We often only get a 3-5 second
 * window from the status reg updating to shutdown, so this is required
 * to give us more accurate polling of the status register.
 */
 
 /* getvoltage - creates a file called "getvoltage". This allows us
 * to poll the battery voltage more frequently than the driver's 1-minute
 * intervals should we want that option for the graphing portion of the
 * calibration app.
 * 
 */
 
 /* getcurrent - creates a file called "getcurrent". This allows 
 *  polling of the battery voltage more frequently than the driver's 1-minute
 * intervals should we want that option for the graphing portion of the
 * calibration app.
 * 
 */
 
 /* getavgcurrent - creates a file called "getavgcurrent". This allows 
 *  polling of the battery voltage more frequently than the driver's 1-minute
 * intervals should we want that option for the graphing portion of the
 * calibration app.
 * 
 */
 
 Additional files added:
 
 age - interface read and write the age scalar register
 voltAE - interface read and write the AEvolt register
 getfull40  - read only the full40 registers (6a & 6b)
 getmah - get the mAh

