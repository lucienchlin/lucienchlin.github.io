---
layout: post
title: Can you remove the "further restriction" imposed by the copyright holder itself under a "modified" GPL license?
subtitle: 原作者改了GPL授權條款增添了額外使用限制，您能依GPL授權本文刪掉這個限制嗎？
tags: [GPL, AGPL, lawsuit, further restriction, CCLC, Neo4j]
---

**Further restriction**在GNU系列的授權條款是一個舉足輕重的關鍵字，一般我譯作「**額外限制**」，它出現的歷史橋段是這句：「_You may not impose any further restrictions on the exercise of the rights granted or affirmed under this License._」(**就本授權條款提供或批準的權利實施，您不能增添額外的限制。**)

這一段話非常重要，一語道破了GPL這類「公眾授權條款(General Public License)」的實踐特性，就是條款要用可以用，大家都可以用、你可以用、我可以用、其他公眾都可以用，但原則上用的時候，原條款內容一字都不能改，若是要稍作調整，最多是以原作者身份進行例外允許的放寬(exception)，萬沒有再收斂原條款預設的授權範圍的。

但是，真的是這樣嗎？

美國第九巡迴上訴法院(The US Court of Appeals for the Ninth Circuit)近期受理了NEO4J與PURETHINK這兩家公司的[上訴案](https://storage.courtlistener.com/recap/gov.uscourts.cand.335295/gov.uscourts.cand.335295.140.0.pdf)，簡要來說，NEO4J採AGPL-3.0+CCLC來釋出它的程式碼，並聲稱它是開源的，然而，它不是。至少不是一般人，或開放源碼定義(Open Source Definition, OSD)認同的開源。

AGPL-3.0授權是開源授權這一點大家沒有爭議，但加上Common Clause License Condition(CCLC)？

CCLC整體而言就是加上一條附款，註稱軟體依主條款來用沒問題，但千萬不能拿來賣(sale)，這個對「賣」的限制，甚至包括收取諮詢費用，都是不行的。也就是說，開源的主條款加上CCLC，基本上這樣的配套，便不再符合一般對開源的理解和定義了。

所以：

 * **PURETHINK認為應該把它刪掉！**
 * **PURETHINK認為應該把它刪掉！**
 * **PURETHINK認為應該把它刪掉！**

PURETHINK的立場是，這明著就是對AGPL-3.0授權條款主文，增添額外的限制，而依據AGPL-3.0本文第7條的規定，後續軟體的使用者，應該有地位可以刪掉它！(_All other non-permissive additional terms are considered “further restrictions” within the meaning of section 10. If the Program as you received it, or any part of it, contains a notice stating that it is governed by this License along with a term that is a further restriction, you may remove that term._)

但是法官不同意，不管是第一審級的法官，或是第二審級的法官，都沒同意PURETHINK這樣的**創思**。

為什麼？轉過來說，在GNU GPL的FAQ，有著這段，Can I modify the GPL and make a modified license?(我可以修改GPL來製作一個改版的授權條款嗎？)：[https://www.gnu.org/licenses/gpl-faq.en.html#ModifyGPL](https://www.gnu.org/licenses/gpl-faq.en.html#ModifyGPL)

GNU Project給的答案是「**可以**」，但必須讓新的條款在名稱上與GPL無關，**不讓人誤會新的條款還是GPL**。所以在法庭審理上，法官不再稱這樣的條款是AGPL-3.0，或稱它為AGPL-3.0+CCLC，而是給它一個暫訂的代稱：「瑞典軟體條款(Sweden Software Licesne)」，因NEO4J母公司的主事務所在瑞典。

所以說，某種程度，此案一二審法官的立場，偏向於原作者改過的AGPL-3.0，已經是一個新的條款，從而，不能說原作者增添條款本身所無之限制予後手，因為這個條款，就是一個新的條款；但另一方面，改過的條款，此案一二審法官也明確指出，不應該再讓它與原條款名稱做牽連，以免造成誤會，也會引發不實的廣告效應(false advertising)。

這個訴訟實例告訴我們，如果**對開源授權的實務管理還未能得心應手前，採修改過開源授權條款發布的軟體，建議不要太急或太有信心就拿去使用**。

你以為它是開源的，但它可能不是。

----

[Facebook發布鏈結](https://www.facebook.com/lucienchenghsia.lin/posts/10216850668098577)