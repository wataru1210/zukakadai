# zukakadai
---marmaid
flowchart LR
st{{学生}}

sys{{教員}}

st --- t1(課題を出す)
st --- t2(期末試験を受ける)
st --- t3(講義中に発言する)
st --- c1(評価の再調査を依頼する)

t1 -.-> ev1(課題採点)
t2 -.-> ev2(期末試験採点)
t3 -.-> ev3(加点記録)
c1 -.-> ev6

ev1 --- sys
ev2 --- sys
ev3 --- sys

ev4(合計点計算) --- sys
ev5(評価登録) --- sys
ev6(再評価する) --- sys

ex1(修正する) -. extends .->  ev6

subgraph 学期中処理
t1
t2
t3
ev1
ev2
ev3
end

subgraph 期末処理
ev4
ev5
end

subgraph 成績調査
direction TB
c1
ev6
ex1
end
