# What Step 8 actually produced, once

Everyone who reviewed this kit said the same thing: it promises you finish a real piece of work
and never shows you one. This is the one. It is here so you can see the shape before you spend an
evening, and compare it against whatever you get.

**Read this before you read the example, because it is a sample of one and you should know exactly
what it is.**

- **The studio is invented.** A six-person ceramics studio, a made-up price list of ten lines, and
  six lines of scribbled notes. No real business, no real numbers, nobody's data.
- **The job was real in shape:** reprice the autumn range, clay is up 18%, and the owner does not
  know whether to touch the mug she is known for. That is the kind of thing Step 8 asks you for.
- **It ran on a machine that already had a lot installed**, not on a clean first evening like
  yours. So treat it as what the step can do rather than as what it will do.
- **Nothing was tidied.** The only change is that five dashes were swapped for commas, because
  this repo does not use them. No wording, no numbers, no structure.
- **The arithmetic was checked** against the price list afterwards, independently. Every figure
  reproduces.

**The part worth noticing.** It refuses to tell her what to charge. Her files do not say what a mug
costs to make, so a percentage would have been a guess dressed as advice, and Step 8 tells Claude
not to do that. Instead it works out the thing her data *can* answer, that freezing the mug forces
a 1.63 times bigger rise on everything else, drafts the letter, and names the one hour of work that
would turn the draft into a decision. A draft with honest holes in it is the intended outcome, not
a failure.

It also caught itself getting a number wrong by a factor of eight, because Step 8 makes it show the
working rather than only the answer. The wrong figure said protecting the mug was cheap. The right
one said it costs about 1% of the business a year.

---

## Autumn repricing, first draft

Built only from `current-prices.csv` and `notes.txt`. Nothing here comes from outside those two files.
There is one number I cannot work out from what you gave me, and it is the most important one. It is at
the bottom under **Gaps**, and I would read that before you read anything else.

---

## Check these three assumptions first

1. **The `units_sold_last_year` column is total units, and about 40% of them went out at the wholesale
   price** (from your note, "wholesale is roughly 40% of volume"). If that column is actually retail-only
   sales, all my cash figures are too low. **Good news: I tested this one, and the mug decision below does
   not move.** At 0% wholesale the key multiplier is 1.629; at 100% it is 1.619. So if I have this wrong,
   the money totals change but the recommendation does not.
2. **Last year's volumes are a fair guide to this autumn's.** I have one year of numbers and no trend, so
   every "this raises £X" figure assumes you sell roughly what you sold last year.
3. **"Reprice the range" means both the retail and the wholesale column.** I have treated them as moving
   together. If you were only planning to move retail, section 3 changes completely.

*And one smaller thing I should own: your files do not say what currency these are in. I have written £
throughout because I had to write something. If it is not £, the symbol is wrong everywhere and none of
the arithmetic is.*

---

## 1. What your range actually is, by money

Blended revenue = units × (40% at wholesale + 60% at retail). Sorted by what each line contributes.

| Item | Size | Units | % of units | Revenue | % of revenue | Wholesale as % of retail |
|---|---|---|---|---|---|---|
| Everyday mug | 300ml | 1,840 | 31.7% | £34,592 | 23.9% | 45.8% |
| Everyday mug | 450ml | 960 | 16.5% | £21,120 | 14.6% | 46.4% |
| Breakfast bowl | medium | 720 | 12.4% | £16,992 | 11.8% | 46.7% |
| Dinner plate | | 530 | 9.1% | £14,204 | 9.8% | 47.1% |
| Planter | | 310 | 5.3% | £13,640 | 9.4% | 46.4% |
| Breakfast bowl | large | 410 | 7.1% | £11,644 | 8.1% | 47.2% |
| Side plate | | 610 | 10.5% | £10,614 | 7.3% | 47.7% |
| Small vase | | 240 | 4.1% | £9,024 | 6.2% | 45.8% |
| Large vase | | 88 | 1.5% | £6,652 | 4.6% | 46.9% |
| Serving platter | | 95 | 1.6% | £6,118 | 4.2% | 46.3% |
| **Total** | | **5,803** | | **£144,601** | | |

Two things fall out of this that you can act on:

- **Your wholesale prices are already a consistent rule.** Every single line sits between 45.8% and 47.7%
  of its retail price. You have effectively been pricing wholesale at "a bit under half of retail" without
  writing it down. That is worth knowing, because it means a straight percentage rise on both columns keeps
  the rule intact, and any line where you deviate is a deliberate decision you will have to explain.
- **Each 1% across the whole range is £1,446 a year.** That is the unit to think in.

## 2. The mug question, answered as far as your data can answer it

This is the bit you said you were scared of, so here is the arithmetic in full rather than the conclusion.

**The two mug sizes are 48.3% of every piece you sell and 38.5% of your revenue.**

If you freeze the mug and raise everything else, the rest of the range has to carry the mug's share too.
The rest of the range is £88,889 of the £144,601 total. So to raise the same cash as a rise of *w* across
everything, the rest has to go up by:

    w × 144,601 ÷ 88,889  =  w × 1.627

**Worked example, and 10% here is an illustration I picked to show the shape, not a recommendation:**

    A 10% rise across everything raises  144,601 × 0.10 = £14,460
    Freezing the mug leaves            144,601 − 55,712 = £88,889 of range to carry it
    That £88,889 must produce £14,460, so it needs   14,460 ÷ 88,889 = 16.27%

So **freezing the mug costs you roughly a 1.63× bigger rise on everything else.** A gentle 10% everywhere
becomes a 16% rise on bowls, plates, vases and planters. And your stockists buy those too, so the two
who complained last time will see a *bigger* number, not a smaller one, precisely because you protected
the mug.

| If you want the cash of a... | ...uniform rise of | ...the rest of the range needs |
|---|---|---|
| smaller move | 5% | 8.1% |
| middling move | 8% | 13.0% |
| larger move | 10% | 16.3% |
| larger still | 12% | 19.5% |

**What I think this means, and it is a judgement not a calculation:** the mug is too big a share of your
business to sit out a repricing. Protecting it does not avoid the problem, it moves the problem onto lines
that are less loved and less defensible. The lever you actually have is not *whether* the mug moves but
*how far* and *to what price point*. At the illustrative 10%, the 300ml mug at 24 rounds to 26, which is
a £2 step on a signature item. Going to 25 instead is worth checking:

    24 → 26 is +8.33%, and 8.33% × £34,592 = £2,883 a year from this line
    24 → 25 is +4.17%, and 4.17% × £34,592 = £1,441 a year
    the £1 you hold back therefore costs about £1,441 a year

That is not nothing. It is a full 1% of the whole business, from one pound on one mug. Which tells you
something useful: on a line this big, the difference between two adjacent price points is a real
decision, not a rounding detail. It is still your call, but make it knowing the number.

## 3. Illustrative price grid

**These are not recommended prices.** I cannot recommend a rate until the gap below is closed. This shows
the arithmetic and the rounding at one example rate so you can see the shape and swap the rate in.

| Item | Size | Retail now | at +10% | rounded | Wholesale now | at +10% | rounded | Each 1% is worth |
|---|---|---|---|---|---|---|---|---|
| Everyday mug | 300ml | 24.00 | 26.40 | **26** | 11.00 | 12.10 | **12.00** | £345.92 |
| Everyday mug | 450ml | 28.00 | 30.80 | **31** | 13.00 | 14.30 | **14.50** | £211.20 |
| Breakfast bowl | medium | 30.00 | 33.00 | **33** | 14.00 | 15.40 | **15.50** | £169.92 |
| Breakfast bowl | large | 36.00 | 39.60 | **40** | 17.00 | 18.70 | **18.50** | £116.44 |
| Dinner plate | | 34.00 | 37.40 | **37** | 16.00 | 17.60 | **17.50** | £142.04 |
| Side plate | | 22.00 | 24.20 | **24** | 10.50 | 11.55 | **11.50** | £106.14 |
| Serving platter | | 82.00 | 90.20 | **90** | 38.00 | 41.80 | **42.00** | £61.18 |
| Small vase | | 48.00 | 52.80 | **53** | 22.00 | 24.20 | **24.00** | £90.24 |
| Large vase | | 96.00 | 105.60 | **106** | 45.00 | 49.50 | **49.50** | £66.53 |
| Planter | | 56.00 | 61.60 | **62** | 26.00 | 28.60 | **28.50** | £136.40 |

One thing to look at while you are in here: the **side plate at 22 against the 300ml mug at 24**. Rounding
at 10% puts them at 24 and 26, so they stay two apart. If you would rather they were further apart, this
repricing is the moment to do it, and it will not read as a price rise, it will read as a tidy-up.

## 4. Draft letter to stockists

Written for the ten who did not complain. See the note after it for the two who did.

> Subject: Price update from [studio], effective [date]
>
> Hello [name],
>
> I am writing with a bit of notice rather than a surprise on your next invoice. Our wholesale prices
> are going up by [X%] from [date]. The new price list is attached.
>
> The short version of why: our stoneware clay went up 18% in September and glaze went up about 6%. Our
> last price change was two years ago and it was around 5%, so we have absorbed two years of costs before
> coming to you with this one.
>
> A few things that are not changing. [Lead times / minimum order / the terms you want to hold, pick
> the ones that are true.] And the everyday mug [stays at £X / moves to £X], because I know it is the
> line that moves for you.
>
> If you have orders already placed for [date range], those are honoured at the old prices.
>
> If this creates a problem at your end, ring me and we will work it out. I would rather have that
> conversation than have you find out from a spreadsheet.
>
> [sign-off]

**On the two who complained last time.** Do not send them this letter cold. Ring them first, a day or
two before the letter goes out, and let them hear the 18% from you. The letter then arrives as
confirmation of a conversation rather than as news. That costs you two phone calls and it is the
cheapest insurance in this whole document.

**What is deliberately blank and why:** [X%] and the effective date, because the rate depends on the
gap below and the date depends on your order book, which I have not seen. Everything else in the letter
is drawn from your notes and is yours to use as it stands.

---

## Gaps: what I do not have, and what each one would change

**1. Cost per piece. This is the big one.** You know clay is up 18% and glaze about 6%. I do not know
what share of a mug's cost is clay, versus glaze, versus your time, versus electricity, versus rent. So
**I cannot tell you what percentage rise covers the increase.** An 18% clay rise does not mean an 18%
price rise, it means an 18% rise on whatever fraction of the cost clay is, which might be a fifth of it,
in which case the pass-through is nearer 4%. Everything above deliberately stops short of naming a rate
for this reason. Anyone who gives you a percentage without this number is guessing.

*What would close it:* for one line, ideally the 300ml mug, the weight of clay in it and what you pay
per bag, the glaze cost, and roughly how many minutes of studio time it takes. One item is enough to get
the ratio, and then the whole range follows. That is an hour with a scale and an invoice.

**2. Kiln electricity per piece.** Your note says it is up but you do not know by how much. Without a
kilowatt-hour rate and a typical firing load I cannot put a number on it. *What would close it:* an old
electricity bill and a new one, plus roughly how many pieces come out of a full firing.

**3. Your labour, and the six people.** No wage costs in the files. If wages have moved in two years,
that is a cost rise sitting outside the 18% and 6% entirely, and it is probably bigger than either.

**4. Whether the range still sells at the new prices.** I have last year's units and no way to know how
sensitive your customers are. Nothing in your files tells me whether a mug at 26 sells like a mug at 24,
and I have not assumed either way.

**5. Your stockist agreements.** I do not know what notice period you owe them, so the letter says
[date]. If any agreement specifies one, it beats anything in this document.

**6. What the two complaints were actually about.** "Grumbled about the last rise" could mean the size of
it, the notice, or their own margin being squeezed. Those need three different answers and I picked none
of them. Worth two minutes of recall before you ring them.
