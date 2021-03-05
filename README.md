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

| Scenario                          | Description | Rendering Time |
| :-------------------------------- | :---------: | -------------: |
| useState with Object              |    Title    |         22.5ms |
| useReducer                        |    Text     |         19.3ms |
| useCallback with useState         |    Text     |         15.4ms |
| useCallback with useReducer       |    Text     |         23.6ms |
| React.memo                        |    Text     |          9.1ms |
| Without Performance Enhancements  |    Text     |         21.4ms |
| All with Performance Enhancements |    Text     |         18.5ms |

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
