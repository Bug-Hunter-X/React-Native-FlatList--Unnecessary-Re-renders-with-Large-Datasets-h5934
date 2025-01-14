# React Native FlatList: Unnecessary Re-renders

This repository demonstrates a common yet subtle bug in React Native's `FlatList` component when handling large datasets. The bug manifests as unnecessary re-renders of list items, leading to performance issues and unexpected behavior.  The problem often arises from improper key management or data mutations within the `renderItem` function.

## Problem Description

The provided example shows a `FlatList` rendering a large dataset.  Due to a flaw in the `keyExtractor` function or data changes within `renderItem`, items are re-rendered more frequently than necessary. This results in dropped frames, slower scrolling, and potentially incorrect UI updates.

## Solution

The solution focuses on ensuring that the `keyExtractor` function provides unique keys for each item and avoiding data modifications that trigger unnecessary re-renders within the `renderItem` function.  If data needs to change, re-render the entire FlatList.