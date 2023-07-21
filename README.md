# White Widow

Chess engine written in C#, compliant with the UCI protocol.

## Board Representation and Move Generation

Positions are represented with 12 [bitboards](https://www.chessprogramming.org/Bitboards), one for each piece type, where each positive bit signifies an occupied square.

Move generation uses [magic bitboards](https://www.chessprogramming.org/Magic_Bitboards) for sliding pieces and pre-computed move data for the others.

## Search

The Search function is based on the [negamax](https://www.chessprogramming.org/Negamax) algorithm, and it uses many popular techniques to improve speed and playing strength, including the following:
- [Alpha-Beta Pruning](https://www.chessprogramming.org/Alpha-Beta)
- [Move Ordering](https://www.chessprogramming.org/Move_Ordering)
- [Quiescence Search](https://www.chessprogramming.org/Quiescence_Search)
- [Transposition Table](https://www.chessprogramming.org/Transposition_Table)
- [Iterative Deepening](https://www.chessprogramming.org/Iterative_Deepening)
- [Aspiration Windows](https://www.chessprogramming.org/Aspiration_Windows)
- [Late Move Reductions (LMR)](https://www.chessprogramming.org/Late_Move_Reductions)
- [Internal Iterative Deepening (IID)](https://www.chessprogramming.org/Internal_Iterative_Deepening)
- [Depth Extensions](https://www.chessprogramming.org/Extensions):
  - [Check Extensions](https://www.chessprogramming.org/Check_Extensions)
  - [Passed Pawn Extensions](https://www.chessprogramming.org/Passed_Pawn_Extensions)
- [Pruning Techniques](https://www.chessprogramming.org/Pruning):
  - [Mate Distance Pruning](https://www.chessprogramming.org/Mate_Distance_Pruning)
  - [Razoring](https://www.chessprogramming.org/Razoring)
  - [Null Move Pruning](https://www.chessprogramming.org/Null_Move_Pruning)
  - [ProbCut](https://www.chessprogramming.org/ProbCut)
  - [Futility Pruning](https://www.chessprogramming.org/Futility_Pruning)
  - [Late Move Pruning (LMP)](https://www.chessprogramming.org/Futility_Pruning#MoveCountBasedPruning)
  - [Standing Pat in Quiescence Search](https://www.chessprogramming.org/Quiescence_Search#StandPat)

## Evaluation

Most of the evaluation constants currently used are from [Stockfish](https://github.com/official-stockfish/Stockfish).

Each score used is separated into an opening value and an endgame value, which are interpolated based on the game phase.

Some of the evaluation features include:
- [Material](https://www.chessprogramming.org/Material)
- [Piece-Square Tables](https://www.chessprogramming.org/Piece-Square_Tables)
- [Mobility](https://www.chessprogramming.org/Mobility)
- [Outposts](https://www.chessprogramming.org/Outposts)
- [Color Weakness](https://www.chessprogramming.org/Color_Weakness)
- [Pawn Structure](https://www.chessprogramming.org/Pawn_Structure)
  - [Passed Pawns](https://www.chessprogramming.org/Passed_Pawn)
  - [Doubled Pawns](https://www.chessprogramming.org/Doubled_Pawn)
  - [Isolated Pawns](https://www.chessprogramming.org/Isolated_Pawn)
  - [Backward Pawns](https://www.chessprogramming.org/Backward_Pawn)
- [Basic King Safety](https://www.chessprogramming.org/King_Safety)
- [Bishop and Knight Pairs](https://www.chessprogramming.org/Bishop_Pair)
