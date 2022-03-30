---
layout: post
title: Upstream not, security pass not.
subtitle: 公司不讓我溯源上傳，產品的資安檢測或許就不容易過。
cover-img: /assets/img/2022-03-30.png
thumbnail-img: /assets/img/2022-03-30-s.png
share-img: /assets/img/2022-03-30.png
tags: [upstream, GPL, community, OpenChain]
---

某RD主管：「顧問，我們交付的項目，裡面有開源軟體被報資安通報，但那個漏洞其實我們是已經補起來的，這時候要怎麼辦？」

----

今天讓我們坦白一點，事實上以現狀來說，臺灣多數的資通訊產業，都是把開源當閉源用。意思就是採用了開源的程式碼，發現有錯或需要調整，都是在local branch進行，然後就把這樣的調校，閉而鎖之，不大會再貢獻回原來上游的源碼庫。

但是長遠來說，這樣真的好嗎？

從現實面來說，
  * 第一點，多數公司並沒有建立流程，讓工程部門可以將調校過的程式碼，溯源回傳(upstream)，因為從公司IP治理的立場，upstream與否，牽涉到公司的經濟利益，並不能讓工程師逕予為之；
  * 第二點，即使是嚴格著作佐特性(strictly copyleft)的開源軟體授權條款，例如GPL-2.0、GPL-3.0、AGPL-3.0，也只是要求提供了binary form就必須連帶能提供source form，這樣的提供義務是向收受產品或binary form的「後手」負責，也並沒有要求開源程式的使用者、改作者，一定要溯源回傳(upstream)。

所以過去多數廠商或其軟體開發人員，秉持著多一事、不如少一事，盡量不找自己麻煩，有要求(要索取源碼)、再補鍋(再提供)的態度來處理源碼要不要提供的問題。

長期來說，這對公司的治理和利益，是不好的。

為什麼？

務實的來說，隨著開源軟體日漸被用於資通訊基礎建設，它所牽涉和可能引發的資安問題，也日漸被注目，例如：

  * 我國[資通安全管理法施行細則第4條第1項第5款](https://law.moj.gov.tw/LawClass/LawSingle.aspx?pcode=A0030303&flno=4)明白要求，當**提供政府機關資通系統的建置、維運，及服務時，利用到非受託者自行開發之系統或資源者，皆應標示非自行開發的內容與其來源及提供授權證明。**這項要求，當然包括開源軟體，以及其他非廠商自主開發的共享軟體(shareware)。
  * 美國總統拜登於2021年5月12日簽署「改善國家網路安全」總統行政命令([Executive Order on Improving the Nation’s Cybersecurity](https://www.nist.gov/itl/executive-order-improving-nations-cybersecurity))，要求未來提供給美國聯邦政府的資通訊服務，必須明確依建議格式列示**軟體套件清單**([Software Bill of Materials, SBOM](https://www.ntia.gov/SBOM))。
  * 美國白宮於今年(2022)初，舉行開源軟體資安高峰會([White House open-source software security summit](https://www.whitehouse.gov/briefing-room/statements-releases/2022/01/13/readout-of-white-house-meeting-on-software-security/))，召集各大資通訊廠商與平台，共商開源資安合作的方向。席間Google出席的代表指出，業界應合作一個託管或列示平台或清單，來處理共通性開源專案的資安問題。

這代表，使用到開源或其他第三方軟體，必須列示清單，以供業主進行資安通報的查察與更新，已經逐步成為一個必要需求。

回到本文一開始，業界RD主管提出來的疑問：「其實我用的開源軟體資安漏洞已經補起來了，但因為我們是在近端補漏，該軟體紀錄上的軟體清單編號還是舊版，所以資安掃描裡被報誤而無法驗收，這該怎麼辦？」

可以溝通、但未必有效。

發生問題時，受委託方當然可以和業主據理力爭，證明資安漏洞掃描出來的問題，其實是false alarm，向業主說明該等漏洞已被補齊，然而，前提是業主願意多花心思去理解，然後個案去核可這樣的狀況進行例外驗收，這容易嗎？

也就是說，若是公司政策仍堅持開源專案的續行開發，軟體工程師不得溯源回傳來修補漏洞，那極端狀態就會產生「你不讓我upstream，我們資安掃描不過。(Upstream not, security pass not.)」的窘境。

基本上，Linux Foundation下[OpenChain](https://www.openchainproject.org/)開源合規流程標準的導入，可以協助處理這個問題。

在[OpenChain開源合規政策書](https://raw.githubusercontent.com/OpenChain-Project/Specification-Translations/master/zh-Hant/2.0/OpenChain-Specification-2-0-zh-Hant.pdf)的第五章，明確提示產業公司，應完備一份書面政策書，來管理公司對開源專案的貢獻，該政策的建議，並不是說迫使公司一定要溯源回傳修改過的開源程式碼，然而完備此份政策書，將可以讓整體利益評估有利於公司營運和產品銷售時，有機會讓工程部門得依循事先規範的流程，來進行對公司有益的源碼上傳。

以救濟目前無論好壞，皆沒有機會進行溯源貢獻的狀態。