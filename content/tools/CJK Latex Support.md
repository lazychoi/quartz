---
title: "CJK + Latex Support (测试)"
---

## Chinese, Japanese, Korean Support
几乎在我们意识到之前，我们已经离开了地面。

우리가 그것을 알기도 전에 우리는 땅을 떠났습니다.

私たちがそれを知るほぼ前に、私たちは地面を離れていました。

## Latex

블록 수식은 달러 기호 두 개로 감싼다.
Block math works with two dollar signs `$$...$$`

$$f(x) = \int_{-\infty}^\infty
    f\hat(\xi),e^{2 \pi i \xi x}
    \,d\xi$$

인라인 수식은 달러 기호 하나로 감싼다. 
Inline math also works with single dollar signs `$...$`. For example, Euler's identity but inline: $e^{i\pi} = -1$

방정식 정렬도 잘 보여진다.
Aligned equations work quite well:

$$
\begin{aligned}
a &= b + c \\ &= e + f \\
\end{aligned}
$$

행렬도 잘 표시된다. And matrices

$$
\begin{bmatrix}
1 & 2 & 3 \\
a & b & c
\end{bmatrix}
$$

## 오른쪽에서 왼쪽으로 쓰는 문자(RTL)
아라비아 문자처럼 오른쪽에서 왼쪽으로 쓰는 언어 설정에 관한 정보는 [config](tools/config.md) 페이지를 참조하라.
More information on configuring RTL languages like Arabic in the [config](tools/config.md) page.
