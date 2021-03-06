# A WEATHER DATASET CASE STUDY



##### MapReduce comes into its own for large datasets

- 데이터셋이 클수록 효율적임
- 데이터의 크기와 상관없이 동일하게 동작하기 때문에
- 시스템이 알아서 데이터와 가까운 곳에서 Map 또는 Reduce 함수를 실행하기 때문에



##### UNIX 분석도구 - 병렬처리의 Potential Problems

- **작업을 똑같은 사이즈로 나누는 것이 어려움**

  - 로드밸런싱 Issue
  - 연도별로 관측되는 사이즈가 다를 수 있음
  - 큰 사이즈의 파일을 처리하는 노드가 더 오래걸림

  **:point_right: 입력을 고정 크기 청크로 나누고 각 청크를 프로세스에 할당하는 것이 더 나은 접근법**



- **각각 프로세스 결과를 합치려면 추가 처리가 필요함**
  - 단일 머신으로 작업할 경우 처리량이 제한되어있음
  - 일부 데이터가 단일 시스템의 용량 이상일 수 있음



- **여러대의 머신을 사용하면 머신들을 조율하는 것과 안정성을 고려해야함**



- **Output 파일은 Reducer당 하나**



##### Context

- Context는 Mapper가 Hadoop 시스템의 나머지 부분과 상호 작용할 수 있도록 해줌
- Job에 대한 설정 데이터와 출력을 방출할 수 있는 인터페이스를 포함



- LongWritable → Java Long
- Text → Java String 
- IntWritable → Java Integer



- Old API: `org.apache.hadoop.mapred`
- New API: `org.apache.hadoop.mapreduce`

