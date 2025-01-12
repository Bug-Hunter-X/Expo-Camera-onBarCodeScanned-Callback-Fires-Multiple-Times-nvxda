# Expo Camera onBarCodeScanned Multiple Trigger Issue

This repository demonstrates a bug in Expo's Camera API where the `onBarCodeScanned` callback function is triggered multiple times for a single barcode scan.  This can lead to performance problems and incorrect application logic.

The `bug.js` file showcases the problem. The `bugSolution.js` file provides a solution to mitigate the multiple triggers.

## Problem:

The `onBarCodeScanned` callback continuously fires as long as the barcode remains visible to the camera.  This is not the intended behavior, and results in multiple identical barcode reads being processed.

## Solution:

The solution involves using a state variable to track the last scanned barcode and only processing a scan if a new barcode is detected.

## How to Reproduce:

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `expo start` to start the Expo development server.
4. Scan a barcode using the app. Observe the console output for multiple entries of the same barcode.

## To fix, refer to bugSolution.js