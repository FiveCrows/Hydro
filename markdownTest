pandoc -f latex -t markdown ./proposal.tex
Introduction
============

This proposal is as an upgrade to the current PIVX consensus/voting
system for passing proposals into community acceptance, which has been
adapted for optimum balance. Currently, it is the foremost consensus
model for both representing and protecting the small investors in the
voting pool.

The following issues to be balanced into this model have been chosen as
follows:

1.  <span>Privacy</span>

2.  <span>Simplicity for the end user</span>

3.  <span>Balance, protection, and respect for all groups of the
    community</span>

4.  <span>Maximation of network value. It is understood that network
    value may have modelled by $V=N^2SI$(described in
    detail below)</span>

5.  <span>Maximization of the total utility the PIVX network provides
    for its end users, who are the real source of its value.</span>

6.  <span>Proper representiation for the general usership is of
    particular concern, because the relationship between a social
    networks value and the quantity\*quality of its members is
    approximately quadratic ($N^2$).</span>

7.  <span>Resistance to vote gaming, agressive system tuning, and
    unhealthy feedback</span>

There are quite a few roles the people who involve themselves with PIVX
may play. Whether it is one or many, these roles will determine their
interests and how they’ll vote. A few of the important ones are listed
below:

Fat cats who move large volume. Some are just wealthy people, but others
come from financial institutions who trade with other peoples money.

From the exchanges, mostly. They like predictable volatility, often use
backtested tradebots, may be trading borrowed currency (margin), and
mercurially come in two flavors:

<span>Bear:</span>

If they are waiting to sell

If they are waiting to buy

Whale traders often proactively push currency value towards the
direction they think it’s already headed. If they are bulls, they may
publically declare it diamonds, and use their votes to, at least
temporarily, raise its price. If they are bearish, however, whale
traders will be most likely trying to push the price down.

Different than traders, because they buy and hold long term. Since they
are healthy to the system, PIVX incentives them with staking and
masternode rewards.

The ones who design improvements. You, presumably.

Selling either goods or services, these people will mostly want low
transaction fees and stable currency values.

Their interests are basically going to be the same as the suppliers.

This model solves many of the various conundrums of voting that result
from currently used voting models, which are starved of information. Our
final challenge is to curtail the arrival of common feedback loop
misbehaviors evident in current politics and common feedback systems.
Some explanation for the exact choices made will be given.

One of the fundamental features of this model is that it offers
leadership to large stake holders (and potentially developers) while
simultaneously securing protection for small investors. This is the
inspiration for the name “PIVX-metheus”.

Note that voting systems are feedback loops that can exhibit unexpected
behaviors. It is unrealistic to assume that one can construct a feedback
loop and have it behave optimally from the very beginning. Therefore it
is strongly suggested to hold the voting system design as experimental
for the first 10 to 15 years. This suggests strongly that for that time
period, a meta-voting system be enabled which allows the voting system
its self to be altered with a model that does not allow for one of the
layers by its self to block the voting system edit. However, such a
meta-voting system should only be activated based on references to
behavior tuning issues. Such tuning issues need to be made visible by
means of building a set of system measures into a system status panel
similar to what we see at this site: http://pivx.masternodes.pro/ only
much more advanced and informative. The existence of such a system
status panel will for many reasons be a substantial addition the value
of the cryptocurrency.

Strategic Weight Analysis
=========================

Derivation of Approach
----------------------

Many issues were brought up and many models and proposals considered for
the purpose of achieving consensus regarding private cryptocurrency
development. We chose a model that made use of many components of other
proposals that were made. Simpler models may have been desirable, but
could not satisfy enough of the fundamental values needed by the system.
These values are:

The fundamental model we begin with is that of the value of a network,
which is approximated by the following equation: $$V=N^2SI$$ where N is
the number of nodes and$ N^2$ the number of possible connections, S the
strength of the connections and I the intelligence of the

The goal is to maximize the value of the network by developing a
feedback model which respects and protects these dimensions of value
seperately, and as accurately as possible. According to the model,
clearly, the value of the network is extremely sensitive to the number
of people using the network. Therefore, in deference to some earlier
models suggested, this document assumes that protection of the $N^2$
element of the network, which is primarily represented by the small
investors, can not be sacrificed.

Because of the above privacy requirement, acquiring extremely accurate
representations of these three value dimensions is not possible without
choosing and using cloaked identity technologies which, while under
development, are not yet proven and trustable in our estimation.
Therefore, we relegate the possibility of using such identity
technologies to future decision making, and strategize to make due with
approximations of the three value dimensions noted above. The resulting
strategy looks very similar to presstab’s original 3 layer proposal, but
is adjusted in order to acquire some of the other values listed above.

It is to be noted at this point that a voting layer is just that. It is
a mathematical entity used to calculate vote value/weight, and not to be
confused with a particular type of node on the network. Simultaneously,
the voting layers would have strong relationships to the types of nodes
and accounts on the network because of the nature of those nodes and
accounts.

Chronology (The No-dancing Filter)
----------------------------------

A consensus model deriving its voting weights simply by what each wallet
is holding at voting time would erroneously overrepresent traders who’d
only recently bought their PIVX. Value comes from those who hold their
PIVs, as should the votes. A good measure for this is the ’Exponential
Moving Average’

$$f(H(t))= \int_{0}^{\infty} e^{-cx}H(t-x)dx$$

Where H(t) represents what the wallet is holding at time t. The EMA has
a few neat properties. If the holdings on a wallet were to suddenly jump
from zero to H, the EMA would steadily respond as $$f(t)=H(1-e^{-ct})$$
If the wallets value jumped back to zero, it’s EMA would respond at the
rate $$f(t)=He^{-ct}$$ Where (H(t)) is the wallet at time t. To be
implemented, the EMA can be calculated by tracking the time and values
between transactions. Suppose the last transaction occured T in the
past:
$$f(H(t))=\int_{0}^{T} e^{-cx}H(t-x)dx+\int_{T}^{\infty} e^{-cx}H(t-x)dx$$
which simplifies to $$f(H(t)) = (1-e^{-cT})H(t)+e^{-cT}f(H(t-T))$$

If it happens these calculations are too cumbersome to perform on every
transaction, an even further simplified model can be used, which simply
approximates a wallets holdings by its contents iteratively say, every
two weeks, so that if $e^{-cT}=C$ and the iteration is n, then
$$f_n=(1-C)H(n)+(C)f_{n-1}$$ The engineers know this equation as an
’IIR’ filter. Smaller C result in faster t decay. If C is needed to
provide a specific decay rate as fractional reduction per interval T,
$0<\lambda<1$, the inversion is quite simple. $$\c=ln(\lambda)$$

Ballots
=======

The main issue is that voters should have no need for ’insincere
voting’. Rather, they should be prompted to include enough information
in their ballot that the voting algorithm can always count their vote
towards the most favorable situation. I expect the majority of my
expected audience for this paper is already familiar the problems with
’first pass to post’ voting, and may be familiar with the apparent
alternatives of both ’iterative ranked’ voting, and +,0,- voting. If you
are, you may wish to skip the next paragraph.

The idea behind iterative ranked is that each ballot consists of an
ordered list of the voters preferences. After the first pass, ballots
may be counted up, and for each voter whose top pick was for a losing
option, his vote gets to be redistributed to his next favored option on
a second iteration.

With +,0,- voting, each option on the ballot recieves a +, -, or
nothing. There are two versions of this, since the + and - options may
or may not be mutually ranked. The rest of this document will consider
only mutually ranked +,0,-. Once the ballots are filled, the +,0,-1
counts are first added together, and as before, votes for the least
desired option will be removed from the ballots before an iterated
recount. If, at any point, each -1 option is removed from a voters
ballot, it is reasonable that said voter gets an implicit -1 count on
his least preferred of the +1 options, and similarly if all +1 options
are eliminated. Implicit -1 to +1 and reverse should not, of course, be
taken in comparison to the null vote

However, many do not appear to have considered the following issue: PIVX
doesn’t intend to rely on elections, if they even choose to have them at
all. The sources of analysis many of the folks on PIVX governance have
been considering are for picking candidates for a particular role, say
’king’, or what have you. However, the PIVX community will be voting on
proposals and ammendments directly, which is uniquely different from an
election, in that the ’null’ option, to change nothing, is present. OK,
so now you may be thinking, sure, all that means is we simply need to
include null within the ranks, so that a ballot for three competing
options may look something like this:

1.  <span>B</span>

2.  <span>A</span>

3.  <span>null</span>

4.  <span>C</span>

This voter would rather see nothing get passed than Option C, because it
is ranked below null. Infact, the same voter could have identically
represented his opinions on this +,0,- style ballot:

1.  <span>B +1</span>

2.  <span>A +1</span>

3.  <span>C -1</span>

Since C is -1 here, it is implicit that it is less preferred than null.
There is no meaning as to whether ranked, is better than +,0,- because
infact, they contain identical identical information, or as a
mathematician would describe it, are ’Isomorphic’. However, I do believe
the ladder, +,0,-1 ballots are simpler for the end user, since they
require no explanation as to what ’null’ means. At the end remains the
task of counting up the votes. In our example here- if the C and NULL
options are eliminated after the first iterated passes, the algorithm
must automatically set preference for B, with +1, against A, with -1.

Some PIVX members have cited the ’Condorcet Paradox’ and its various
derivatives as arguments against ranked systems. However, if you look at
them carefully, you may notice that the real problem amounts to the fact
that items can get symmetric voting. Objectively, these theorems are not
paradoxes at all, but trivial; when all the options get the same number
of votes, in any system, obviously that’s a problem.

Another concern is how this system could be integrated into more complex
macro-model, with multiple layers and so forth. Although I can’t specify
which is best until the actual full voting algorithm is specified, there
are a few very effective ways to integrate votes from different layers:

-   <span>Perhaps the simplest solution is just to add all the votes
    from different voting layers into one pool, differentiating them
    only by the algorithms that determine their weighting</span>

-   <span>A specialized tactic would be to rank the canditates into a
    macrovote, by progressively removing the previous winner from the
    ballots, in order to determine the next most preffered option. You
    could even keep track of the precise margin each winner recieved,
    but then again, if we wanted that functionality we’d have just used
    the first option listed here.</span>

-   <span>it may be strategic to allow layers to block ammendments that
    they have a negative opinion about, meaning the option ranks bellow
    null</span>

Implementation
==============
