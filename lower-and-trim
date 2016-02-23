///	This loop takes all string variables in the data, converts them to lowercase,
///	and removes excess spaces before, within, and after each word of the string
///		Numbers to right of each line are explained in notes below

sysuse auto, clear

l make in 1/5

*	lowcase & trim
qui ds, has(type string)				/*	1	*/		
foreach v of varlist `r(varlist)' {		/*	2	*/
	replace `v'=lower(`v')				/*	3	*/
	replace `v'=itrim(`v')				/*	4	*/
	replace `v'=trim(`v')				/*	5	*/
}

l make in 1/5

/*	NOTES:
	1:	lists string variables, stores them in `r(varlist)' macro
	2:	initiates loop for each string variable identified in 1
	3:	converts string to all lowercase letters
	4:	removes gaps between words of more than 1 space
	5:	removes spaces before first word or after last word
*/


*	example
clear
input str20 color num
blue 3
red 23
GREEN 2						/*	unwanted upper case letters	*/
"dark     brown" 23			/*	unwanted large space between words	*/
"   burnt umber  " 3		/*	unwanted spaces before first and last words	*/
end

l color num in 1/5

qui ds, has(type string)					
foreach v of varlist `r(varlist)' {
	replace `v'=lower(`v')
	replace `v'=itrim(`v')
	replace `v'=trim(`v')
}

l color num in 1/5
