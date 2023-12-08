REPORT ZCURSO_007.

SELECTION-SCREEN BEGIN OF BLOCK b1.
  PARAMETER: p_1bim(12) TYPE p DECIMALS 2.
  PARAMETER: p_2bim(12) TYPE p DECIMALS 2.
  PARAMETER: p_3bim(12) TYPE p DECIMALS 2.
  PARAMETER: p_4bim(12) TYPE p DECIMALS 2.
SELECTION-SCREEN END OF BLOCK b1.

START-OF-SELECTION.
  DATA ld_media TYPE p DECIMALS 2.

  ld_media = ( p_1bim + p_2bim + p_3bim + p_4bim ) / 4.

" OPERADORES
" =
" <>
" >
" >=
" <
" <=
" <=
" NOT COLOCA ANTES DA EXPRESSÃO ELE INVERTE O RESULTADO DA CONDIÇÃO OU EXPRESSÃO


IF ld_media < 60. " SE
  WRITE: 'Sua média anual foi de ', ld_media, ' , você foi reprovado.'.
ELSE. "SENÃO
  WRITE: 'Sua média anual foi de ', ld_media, ' , você foi aprovado.'.
ENDIF.

* COMBINAÇÕES de AND e OR
* verdadeiro AND verdadeiro = verdadeiro.
* verdadeiro AND falso      = falso.
* falso      AND verdadeiro = falso.
* falso      AND falso      = falso.

* verdadeiro OR verdadeiro = verdadeiro.
* verdadeiro OR falso      = verdadeiro.
* falso      OR verdadeiro = verdadeiro.
* falso      OR falso      = falso.

IF ld_media >= 0 AND ld_media <= 50.
  WRITE: 'Sua nota foi muito baixa, você foi reprovado.'.
ELSEIF ld_media >= 51 AND ld_media <= 59.
  WRITE: 'Você quase passou, estude um pouco mais'.
ELSEIF ld_media >= 60 AND ld_media <= 100.
  WRITE: 'Parabéns, você passou!'.
ENDIF.
