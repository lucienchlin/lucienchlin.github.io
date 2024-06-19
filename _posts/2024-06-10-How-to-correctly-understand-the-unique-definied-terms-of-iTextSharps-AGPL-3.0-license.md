---
layout: post
title: How-to-correctly-understand-the-unique-definied-terms-of-iTextSharp's-AGPL-3.0-license
subtitle: 如何正確理解iTextSharp獨具一格的AGPL-3.0
cover-img: /assets/img/2024-06-10.png
thumbnail-img: /assets/img/2024-06-10.png
share-img: /assets/img/2024-06-10.png
tags: [pdf, AGPL, copyrighttroll, copytroll, itext, output, rejectedlist, Asia, Taiwan]
---

如果您對AGPL-3.0的授權拘束特性並不熟悉，或是您組織裡並沒有專務進行開源合規調處的職員，那建議不要去使用到，**iText/iTextSharp在v.5之後的AGPL-3.0授權版本**。因為我們末必能有信心說，它真的是開源的軟體。依過去的司法實例，或許它所採用的條款，該被改稱為 iText Belgium Software License 或 iText Canada Software License，這樣才不會產生使用上的誤解和誤會。

進一步說，大增額外條款的AGPL-3.0，還會是大眾認知開源授權的AGPL-3.0嗎？或者說，您知道**iTextSharp在過去幾年一直在亞洲各地寄發侵權或開源不合規的警告信件給商業公司或政府部門**嗎？主要這些警告信的使力點，在於AGPL-3.0授權要求，在修改原AGPL-3.0程式碼並用作網路服務時，必須揭露原出處的顯名聲明，並且應使用者要求，來提供該AGPL-3.0能被後續改作的程式源碼；另外，AGPL-3.0在第7條加立了「額外條款(Additional Terms)」的機制，這讓它在應用和合規處理上，更形複雜而不易處理。

大致的狀況是這樣：
1. AGPL-3.0和GPL-3.0授權條款類同，要求散布(convey)了原程式後，必須[應要求提供後手相應的程式源碼](AGPL3.0 6. Conveying Non-Source Forms)。
2. 一般來說，前項義務是在程式碼被實體散布之後，才會啟動，例如燒錄光碟進行發送、提供app下載，或販售嵌入式裝置時啟動。
3. 然而AGPL-3.0在第13條增列要求，若是被授權人確實修改了AGPL-3.0授權的軟體(if you modify the Program)，並將其置於電腦網路來與其他使用者互動(all users interacting with it remotely through a computer network)，那麼此時就必須[加碼讓使用者可以採合理手段向被授權人索取這些經修改過的AGPL-3.0程式源碼](AGPL3.0 13. Remote Network Interaction)。

那麼我們必須具體理解，為什麼AGPL-3.0在2007年新訂時，會有前述微調自GPL-3.0的不同特性：
1. 給了Binary Form就要提供機會讓人索取Source Form、給了Object Code就要提供機會讓人索取Soure Code，是GPL授權類別，對於軟體自由(Software Freedom)理念的追尋；
2. 但很多應用GPL軟體的商業公司扣緊在雲端的環境下，Binary Form並沒有提供，從而也不會進一步提供Source Form給使用者；
3. 從而2007年GPL從2.0更新到3.0新版時，平行增加了一個GPL-3.0的攣生條款AGPL-3.0，AGPL-3.0全文和GPL-3.0一致，然於第13條裡產生差異，明確要求在雲端提供服務的環境下，若該AGPL-3.0的程式「已經改作(if you modify the Program)」，那麼雲端服務方必須揭露並保留該AGPL-3.0軟體的顯名聲明，並且應遠距使用者的要求，接續提供該AGPL-3.0授權軟體的程式源碼給遠距使用者。

然而，iText/iTextSharp在v.5之後延續其開發並提供商業服務的商業公司[Apryse](https://itextpdf.com/)，對於AGPL-3.0的應用，在其原本的基礎更形擴張，其透過額外聲明主張：
1. AGPL-3.0第7條增訂額外條款(Additional Terms)之機制，其中 b) 項讓散布者可以加註另外客製化的合理聲明，讓表彰作者的顯名聲明，就此，Apryse另訂了繁複的顯名聲明。
2. 並且要求這些顯名聲明必須出現的地方，包括採用iText/iTextSharp所轉出來的每一份PDF文件，不論其為電子格式或紙本格式。此要求出現在itextsharp/LICENSE.md這個檔案。[In accordance with Section 7(b) of the GNU Affero General Public License, a covered work must retain the producer line in every PDF that is created or manipulated using iText.](https://github.com/itext/itextsharp/blob/develop/LICENSE.md)
3. 更進一步，Apryse於其官網上表達「使用AGPL-3.0授權iText/iTextSharp軟體，則提供網路服務時，所有自撰的應用程式，包括其他網通程式都必須都採AGPL-3.0釋出！[You may not deploy it on a network without disclosing the full source code of your own applications under the AGPL license. You must distribute all source code, including your own product and web-based applications.](https://itextpdf.com/how-buy/AGPLv3-license)

Apryse這樣的聲明不是沒有爭議的，主要幾項爭議點有：
1. AGPL-3.0的授權條款本文，從來沒有說沾到它的其他軟體，都必須一定被同化拘束採AGPL-3.0釋出，在授權拘束性的範圍，它還是回歸「對應源碼(Corresponding Source)」的範圍，意指重現、安裝該AGPL-3.0軟體，所需要的各相關程式碼就應該是源碼的範圍，然而，該範圍明示排除系統函式庫(System Libraries)以及普遍用途的工具及相關工具組，例如GCC等得使自由應用的開源編譯器。這些規定在AGPL-3.0 1. Source Code 的定義段，與之相較，Apryse官網對應提供源碼的聲明，顯然逾越了AGPL-3.0本文的定義範圍。
2. Work是Work、Output是Output。簡要來說，修改原程式產生衍生程式，不管原程式或衍生程式，都是AGPL-3.0定義的covered work範圍(A “covered work” means either the unmodified Program or a work based on the Program.)，然而，應用該AGPL-3.0程式所進行成果輸出(Output)，並不在covered work的範圍之內。AGPL-3.0此處的原文為「執行AGPL-3.0軟體所產生的輸出，僅在該輸出就內容而言，已構成衍生著作時，才受此授權條款的拘束。(The output from running a covered work is covered by this License only if the output, given its content, constitutes a covered work.)也就是說，使用MS Office來作簡報，不會讓MS取得該簡報的著作分潤，除非該簡報的內容包括MS授權的美術、圖表等，那麼，使用iText/iTextSharp進行PDF轉檔，這些轉檔輸出內含iText/iTextSharp必要的meta-data，也不應被解讀為covered work，從而既然不是covered work，自然不該有 AGPL-3.0 7(b)額外條款的適用空間，因AGPL-3.0 7(b)明文顯示，這些額外條款應該只能加諸於AGPL-3.0授權程式的本身及其添附的素材(for material you add to a covered work)，而不及於單純輸出的範圍。
3. 所以說，AGPL-3.0 7(b)額外條款並不能直接適用於Output發揮效力，那麼加上這些額外的要求，恰恰構成AGPL-3.0要求條款的應用者「不得向後手添加的額外使用限制(You may not impose any further restrictions on the exercise of the rights granted or affirmed under this License)」。當這些額外限制的添加者，為所發布軟體的原始著作權利人時，國外的司法實務並不認為這些添附條款全然無效，在[美國第九巡迴上訴法院(The US Court of Appeals for the Ninth Circuit)2022年受理NEO4J與PURETHINK這兩家公司的上訴案](https://lucienchlin.github.io/2022-03-27-can-you-remove-the-further-restriction-imposed-by-the-copyright-holder-itself-under-a-modified-GPL-license/)裡，我們也明確了解，一二審法官並沒有否定權利人另添條款的效力，然皆指出，實質有修改過的條款，不應該再讓它與原開源條款名稱做牽連，以免造成誤會，也會引發不實的廣告效應(false advertising)！該案NEO4J聲稱其採AGPL-3.0釋出軟體，然法官庭訊文件指出，應稱其為「Neo4j Sweden Software License」，而不要再自稱AGPL-3.0。
4. 最後，AGPL-3.0就第13條的遠距拘束的啟動條件，多數開源社群皆認同其為AGPL-3.0軟體被實質修改後(if you modify the Program)，因為若未經修改，原則上直接揭露所使用的AGPL-3.0軟體版本號即可，有意願再利用該軟體之人，依此版本號自行下載原典即可。然而，Apryse在許多公開論壇指出，即使單純依iText/iTextSharp之APIs來與其互動，多數狀況即為構成iText/iTextSharp軟體程式本身的修改，從而啟動其雲端拘束特性？這樣的論點與過去20年開源技術領域的多數共論，實有顯著差異。
5. 綜合以上的分析，若依NEO4J司法訴訟案的處理，Apryse或許不能再混淆式的簡稱經由其添加額外使用限制的iText/iTextSharp仍是採用AGPL-3.0開源發布，而應該改稱其所採用的授權條款，為 iText Belgium Software License 或 iText Canada Software License，這樣才不會產生使用上的誤解和誤會。

那麼，在非亞洲地區過去是如何處理這樣的爭議的呢？客觀觀察到的有：
1. iText/iTextSharp 4.1.6是最後一版採MPL-1.1/LGPL-2.0+雙授權的版本：[https://github.com/schourode/iTextSharp-LGPL/tree/master](https://github.com/schourode/iTextSharp-LGPL/tree/master)
2. 《使用iText/iTextSharp舊版軟體來進行商業延展開發，可以或是不可以？》：[https://web.archive.org/web/20240314224137/https://kb.itextpdf.com/it5kb/can-itext-2-1-7-itextsharp-4-1-6-or-earlier-be-use](https://web.archive.org/web/20240314224137/https://kb.itextpdf.com/it5kb/can-itext-2-1-7-itextsharp-4-1-6-or-earlier-be-use)
3. 依據前列iText/iTextSharp原文，該公司建議大家不要再用舊版的iTextSharp來進行商用，希望大家採用AGPL-3.0授權的iTextSharp 5及其後更新版本。公司端的理由是：
  * 舊版有些來自SUN的legacy code，這些並非開源的程式碼，繼續使用也會有相關法律風險，
  * 舊版資安狀態必須自行維護，
  * 舊版程式碼不少來自社群參與者個人的貢獻，iText/iTextSharp公司無法依CLA具體取得這些人的承諾，所以繼續使用iTextSharp舊版作為產品開發，潛藏這些不確定要素。
4. 然而不用舊版，新版的iText/iTextSharp，確實會於合規認識不清時，未經原廠告知AGPL-3.0 30天修復期(cure the violation prior to 30 days after your receipt of the notice)，即被原廠寄發警告信，並被要求加買商業授權份數的狀況。
5. 為了顧及更新性，舊授權版本的iText有一個活躍的分支--OpenPDF：[https://github.com/LibrePDF/OpenPDF](https://github.com/LibrePDF/OpenPDF)，保留了 LGPL-2.1/MPL-2.0雙授權，同時更新它的資安狀態，也有若干專案使用。
6. 或者改採用由Apache基金會支持的Apache FOP專案：[https://xmlgraphics.apache.org/fop/](https://xmlgraphics.apache.org/fop/)，基本上ASF提供的開源軟體，皆採寬鬆類的Apache-2.0授權發布。

本文無意直接非難Apryse就其iText/iTextSharp軟體進行商營所採取的推展模式，然而採開源軟體授權發布者，其解釋與應用，還是應該回歸社群常態與產業共識，畢竟開源的奧義在於多元協作、多元共通，任何一款開源授權條款皆非單一作者、單一權利人、單一託管公司在使用，故當其解釋條款的立場特殊或獨排眾議，為免公眾誤踏灰色地帶，還是應該回歸到開源合規的重要教範，亦即：(1)使用開源軟體、便應尊重其隨程式碼發布的授權條款，也就是背後的授權規則，(2)然若無法明確掌握這些授權規則，則不應繼續使用為宜，另外、善於發揮開源方案多元採納的精神，當特定專案因技術、資安或授權相容問題不合使用，可探尋另外平行的替代方案，例如Apache FOP或其他解方，來簡化商業應用上的相關爭議。

----

If you're not familiar with the reciprocal nature of the AGPL-3.0 license or if your organization lacks staff dedicated to handling FOSS compliance, **it's advisable not to use versions of iText/iTextSharp licensed under AGPL-3.0 after v.5**. We can't be confident that it's truly Free and Open Source Software.

Furthermore, with the extensive additional terms of AGPL-3.0, will the license applied by iText/iTextSharp after v.5 still be recognized as the AGPL-3.0 commonly understood by the public? Or, **are you aware that the company hosting iTextSharp has been sending infringement or FOSS non-compliance warning letters to commercial companies or even government departments across Asia for the past few years?** The main focus of these warning letters is on the requirements of the AGPL-3.0 license, which mandates that when modifying original AGPL-3.0 software and using it as a web service, the provider must disclose the original source's prominent attribution and, upon request, provide the modified AGPL-3.0 Source Code for subsequent modifications. Additionally, AGPL-3.0 introduces the mechanism of "**Additional Terms**" in Article 7, making it more complex and difficult to handle in application and compliance management.

The general situation is as follows:
1. The AGPL-3.0 and GPL-3.0 license terms are similar, [requiring the provision of Corresponding Source Code upon distribution of the original program when requested](AGPL3.0 6. Conveying Non-Source Forms).
2. Typically, this obligation is triggered after the software has been physically distributed, such as burning CDs for distribution, providing app downloads, or selling embedded devices.
3. However, AGPL-3.0 adds a requirement in Article 13 that if a licensee modifies the AGPL-3.0 licensed software and makes it available over a computer network for interaction with other users, [the SaaS provider must also provide the modified AGPL-3.0 Corresponding Source Code to remote users upon request](AGPL3.0 13. Remote Network Interaction).

So, we need to understand why AGPL-3.0, when revised in 2007, had these slight adjustments from GPL-3.0:
1. It aims to uphold the pursuit of Software Freedom by requiring that providing the Binary Form offers the opportunity for people to request the Source Form.
2. Many commercial companies using GPL software are heavily focused on cloud environments where Binary Form isn't provided, thus not providing Source Form to users.
3. Therefore, when GPL was updated from 2.0 to 3.0, a parallel addition was made: AGPL-3.0. While the text of AGPL-3.0 is consistent with GPL-3.0, it introduces a difference in Article 13, explicitly requiring disclosure and retention of prominent notices of AGPL-3.0 software used in cloud services environments when the AGPL-3.0 program "has been modified" and making the modified AGPL-3.0 program Corresponding Source Code available to remote users upon request.

However, [Apryse](https://itextpdf.com/), the commercial company continuing development and offering commercial services for iText/iTextSharp after v.5, has expanded the application of AGPL-3.0 on its original basis. They assert through additional statements:
1. The mechanism of adding Additional Terms in Article 7 of AGPL-3.0 allows distributors to add specified reasonable legal notices or author attributions to recognize authors. Apryse has added complex prominent notices accordingly.
2. They require these prominent notices to appear in every PDF file produced or manipulated using iText/iTextSharp, regardless of whether it is in electronic or paper form. This requirement is stated in the [itextsharp/LICENSE.md](https://github.com/itext/itextsharp/blob/develop/LICENSE.md) file.
3. Moreover, Apryse states on its website that [the AGPL-3.0 licensees may not deploy iText/iTextSharp on a network without disclosing the full source code of their own applications under the AGPL license. And it requires the licensees must distribute all source code, including their own product and web-based applications.](https://itextpdf.com/how-buy/AGPLv3-license)

Apryse's statements are not without controversy. The main points of contention include:
1. The text of the AGPL-3.0 license terms never stipulates that all the other software that merely works with it must be uniformly bound to release under AGPL-3.0. The scope of licensing inheritance returns to the range of "Corresponding Source," which means the code needed to reproduce and install the AGPL-3.0 software should be within the scope of Source Code. However, Apryse's website's statement on providing source code clearly exceeds the scope defined in the AGPL-3.0 text.
2. Work is Work, Output is Output. In essence, modifying the original software Work to create derivative software Work, whether the original program or the derivative one, falls within the scope of the covered work as defined by AGPL-3.0. However, the results output from using or working with the AGPL-3.0 program are not undoubtedly within the covered work scope. Therefore, the additional requirements imposed by AGPL-3.0 7(b) do not directly apply to Output. By imposing these additional attribution by Apryse on PDF Output, it might effectively violate the provision of AGPL-3.0 that prohibits further restrictions on the rights granted under the license.
3. Since the AGPL-3.0 7(b) additional terms cannot directly apply to Output. Therefore, adding these additional obligation constitutes imposing further use restrictions in violation of the AGPL-3.0 requirement that no further restrictions can be imposed on the rights granted under the AGPL-3.0 license. In [a recent case involving NEO4J and PURETHINK, the US Court of Appeals for the Ninth Circuit in 2022](https://lucienchlin.github.io/2022-03-27-can-you-remove-the-further-restriction-imposed-by-the-copyright-holder-itself-under-a-modified-GPL-license/) did not deny the effectiveness of additional terms added by the copyright holder itself but pointed out the necessity of clarity to avoid misunderstandings and false advertising. The court instructed NEO4J not to refer to its software as AGPL-3.0 but rather as a variation that can be named as "Neo4j Sweden Software License."

Ultimately, many FOSS communities agree that the trigger condition for the remote restriction in Article 13 of AGPL-3.0 is when the AGPL-3.0 software has been substantially modified. However, Apryse has argued in many public forums that even simply interacting with iText/iTextSharp through its APIs often constitutes modification of the iText/iTextSharp software program itself, thus triggering its cloud restriction feature. This argument differs significantly from the consensus in the FOSS technology field over the past 20 years.

So, how have similar controversies been handled in non-Asian regions in the past? Objectively observed methods include:
1. iText/iTextSharp 4.1.6 is the last version with dual licensing under MPL-1.1/LGPL-2.0+ :[https://github.com/schourode/iTextSharp-LGPL/tree/master](https://github.com/schourode/iTextSharp-LGPL/tree/master)
2. The company that hosts new versions of iText/iTextsharp recommends against using older versions of iText/iTextSharp for commercial development, urging adoption of AGPL-3.0 licensed iTextSharp, v.5 and later updates.
3. Opinions from the hosting company for "Can iText 2.1.7 / iTextSharp 4.1.6 or earlier be used commercially?" can be found here: [https://web.archive.org/web/20240314224137/https://kb.itextpdf.com/it5kb/can-itext-2-1-7-itextsharp-4-1-6-or-earlier-be-use](https://web.archive.org/web/20240314224137/https://kb.itextpdf.com/it5kb/can-itext-2-1-7-itextsharp-4-1-6-or-earlier-be-use)
4. However, if the users adopting the AGPL-3.0 iText/iTextSharp and cannot comply well with the compliance issue, warning letters are issued by the hosting company, and the curement of the violation prior to 30 days after the receipt of the warning notice is not even introduced in most of the disputed cases.
5. To address update concerns, there's an active branch of former licensed versions called OpenPDF: [https://github.com/LibrePDF/OpenPDF](https://github.com/LibrePDF/OpenPDF), which retains LGPL-2.1/MPL-2.0 dual licensing and updates security status.
6. Alternatively, the Apache FOP project supported by the Apache Foundation could be used: [https://xmlgraphics.apache.org/fop/](https://xmlgraphics.apache.org/fop/), as ASF provides FOSS software under permissive licenses such as Apache-2.0.

This article is not intended to directly criticize Apryse's business promotion model regarding its iText/iTextSharp software. However, when adopting FOSS licenses, explanations and applications should still adhere to community norms and industry consensus. After all, the essence of FOSS lies in diverse collaboration.