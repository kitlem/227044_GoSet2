package main

import (
	"fmt"
	"math"
	"strings"
)

func main() {
	var letter string
	var shift int

	fmt.Print("Input a letter: ")
	fmt.Scan(&letter)

	letter_uppercase := strings.ToUpper(letter)

	if len(letter_uppercase) == 1 {
		fmt.Println("Select a number from 1-25: ")
		fmt.Scan(&shift)

		if shift >= 1 && shift <= 26 {
			result := shiftLetter(letter_uppercase, shift)
			fmt.Println("Shifted Letter: ", result)
		} else {
			fmt.Println("Invalid shift value, please try again")
		}
	} else {
		fmt.Println("Invalid input. Please enter a single letter.")
	}
}

func shiftLetter(letter string, shift int) string {

	alphabet := []string{"A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"}
	// searching for the letter index within the slice
	var index int
	for i, char := range alphabet {
		if char == letter {
			index = i
			break
		}

	}
	index_final := (index + shift) % len(alphabet)
	return alphabet[index_final]
}

// Caesar cipher

func main() {
	var message string
	var shift int

	fmt.Print("Input a message: ")
	fmt.Scan(&message)
	message_uppercase := strings.ToUpper(message)

	fmt.Println("Select a number from 1-25: ")
	fmt.Scan(&shift)
	if shift >= 1 && shift <= 26 {
		result := caesarCipher(message_uppercase, shift)
		fmt.Println("Shifted Message: ", result)
	} else {
		fmt.Println("Invalid shift, please try again")
	}
}

func caesarCipher(message string, shift int) string {
	alphabet := []string{"A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"}
	Shift_message := ""
	// checks if the character will contain a space
	for _, letter := range message {
		if letter == ' ' {
			Shift_message += " "
			continue
		}
		// searching for the letter index within the slice
		var index int
		for i, char := range alphabet {
			if string(letter) == char {
				index = i
				break
			}
		}
		final_index := (index + shift) % len(alphabet)
		Shift_message += alphabet[final_index]
	}
	return Shift_message
}

// Shift by letter
func main() {
	var letter string
	var letterShift string

	fmt.Print("Input a letter: ")
	fmt.Scan(&letter)

	letter_uppercase := strings.ToUpper(letter)
	fmt.Print("Select another letter to determine the shift: ")
	fmt.Scan(&letterShift)
	letterShift_uppercase := strings.ToUpper(letterShift)

	if len(letter_uppercase) == 1 && len(letterShift_uppercase) == 1 {
		result := shiftbyLetter(letter_uppercase, letterShift_uppercase)
		fmt.Println("Shifted Letter:", result)
	} else {
		fmt.Println("Invalid Input. Please try again")
	}
}

func shiftbyLetter(letter string, letterShift string) string {
	alphabet := []string{"A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"}

	// searching for the letter index within the slice
	var index int
	for i, char := range alphabet {
		if char == letter {
			index = i
			break
		}
	}
	// shift will iterate through the entire array (a letter equal to the LetterShift and retrieve its index)
	var shift int
	for i, char := range alphabet {
		if char == letterShift {
			shift = i + 1
			break
		}
	}
	final_index := (index + shift) % len(alphabet)
	return alphabet[final_index]
}

// Vigenere cipher

func main() {
	var message string
	var key string

	fmt.Print("Input a message: ")
	fmt.Scan(&message)
	message_uppercase := strings.ToUpper(message)

	fmt.Print("Input a letter: ")
	fmt.Scan(&key)
	key_uppercase := strings.ToUpper(key)

	if len(key_uppercase) == 1 {
		result := vigenereCipher(message_uppercase, key_uppercase)
		fmt.Println("Shifted Message: ", result)
	} else {
		fmt.Println("Invalid Input, Please input 1 letter")
	}

}

func vigenereCipher(message string, key string) string {

	Shift_message := ""
	alphabet := []string{"A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"}

	// shift will iterate through the entire array
	var shift int
	for i, char := range alphabet {
		if string(key) == char {
			shift = i + 1
			break
		}
	}
	// iterating over each in letter
	for _, letter := range message {
		if letter == ' ' {
			Shift_message += " "
			continue
		}
		// searching for the letter index within the slice
		var index int
		for i, char := range alphabet {
			if string(letter) == char {
				index = i
				break
			}
		}

		// showing final shift with the modulo
		index_final := (index + shift) % len(alphabet)
		Shift_message += alphabet[index_final]
	}
	return Shift_message
}

// Scytale cipher
func main() {
	var message string
	var shift int

	fmt.Print("Input a message: ")
	fmt.Scan(&message)
	message_uppercase := strings.ToUpper(message)

	fmt.Print("Input a shift value: ")
	fmt.Scan(&shift)

	if shift > 0 && shift < len(message_uppercase) {
		result := scytaleCipher(message_uppercase, shift)
		fmt.Println("Encoded Message:", result)
	} else {
		fmt.Println("Invalid value, please try again")
	}
}

func scytaleCipher(message string, shift int) string {
	// rounding up to ensure that every column will have space for the character
	rows := int(math.Ceil(float64(len(message)) / float64(shift)))
	// creating a slice using the message user input
	message_to_encode := make([]string, len(message))

	// incrementing the iteration by 1
	for i := 0; i < len(message); i++ {
		// using code given from the prompt
		index_new := (i / shift) + rows*(i%shift)
		message_to_encode[index_new] = string(message[i])
	}

	// concatenate 2 strings together to ensure that the space is removed from the slice
	return strings.Join(message_to_encode, "")
}

// Scytale decipher
func main() {
	var message string
	var shift int

	fmt.Print("Input a message: ")
	fmt.Scan(&message)
	message_uppercase := strings.ToUpper(message)

	fmt.Print("Input a shift value: ")
	fmt.Scan(&shift)

	if shift > 0 && shift < len(message_uppercase) {
		result := scytaleDecipher(message_uppercase, shift)
		fmt.Println("Decoded Message:", result)
	} else {
		fmt.Println("Invalid value, please try again")
	}
}

func scytaleDecipher(message string, shift int) string {
	// rounding up to ensure that every column will have space for the character
	rows := int(math.Ceil(float64(len(message)) / float64(shift)))
	// creating a slice using the message user input
	message_to_decode := make([]string, len(message))
	// incrementing the iteration by 1
	for i := 0; i < len(message); i++ {
		// adjusted this to where the characters can find the correct row
		previous_index := (i%shift)*rows + (i / shift)
		message_to_decode[previous_index] = string(message[i])
	}

	// concatenate 2 strings together to ensure that the space is removed from the slice
	return strings.Join(message_to_decode, "")
}
