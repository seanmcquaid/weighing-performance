# Weighing Performance

This repo will serve as an area to experiment with some performance enhancement concepts in React. To keep it consistent, I am going to use the exact same tasks :

1. Data Fetching on load
2. Forms

I will do one version without any enhancements and then one with the enhancements identified for each concept to see how much is saved for each addition. Then I will try putting it all together and seeing if the React Dev Tools Profiler confirms what I believe

## Forms

Steps for Testing Times :

1. First Name - hello
2. Last Name - there
3. Submit

| Scenario                          |                                       Description                                       | Rendering Time |
| :-------------------------------- | :-------------------------------------------------------------------------------------: | -------------: |
| useState with an Object           |                      Using an object with useState to manage state                      |         22.5ms |
| useReducer                        |                     Using a reducer with useReducer to manage state                     |         19.3ms |
| useState + useCallback            |           Wrapping the onChange functions utilizing useState with useCallback           |         15.4ms |
| useReducer + useCallback          | Wrapping the onChange functions utilizing the dispatch from useReducer with useCallback |         23.6ms |
| React.memo                        |             Wrapping some components with React.memo to reduce re-rendering             |          9.1ms |
| Without Performance Enhancements  |                       Not utilizing any performance enhancements                        |         21.4ms |
| All with Performance Enhancements |                       Utilizing multiple performance enhancements                       |         18.5ms |

## Data Fetching

Steps for Testing Times :

1. Wait for data to load

| Scenario                   | Description | Rendering Time |
| :------------------------- | :---------: | -------------: |
| Batching multiple setState |    Title    |          5.4ms |
| setState with an Object    |    Text     |          5.6ms |
| useReducer                 |    Text     |          6.2ms |

## Form + Data Fetching

Steps for Testing Times :

1. Description - python
2. Location - new york
3. Submit
4. Wait for data to load

| Scenario                          | Description | Rendering Time |
| :-------------------------------- | :---------: | -------------: |
| Without Performance Optimizations |    Title    |         12.6ms |
| With Performance Optimizations    |    Text     |         12.2ms |
