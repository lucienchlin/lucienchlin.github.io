---
layout: post
title: The Open Source Disclaimer might be Compromised to an Extend in the Commercial Environment
subtitle: 提供商用就無法完全免責，即使它本來是開源軟體！
cover-img: /assets/img/2022-04-26.png
thumbnail-img: /assets/img/2022-04-26.png
share-img: /assets/img/2022-04-26.png
tags: [disclaimer, warranty, responsibility]
---

若是**無償發布開源軟體，它的免責聲明就能發揮最大的免責效用，然若是有償提供，則提供者能主張的免責範圍當會受到相當限縮！**

我一直都很想翻譯Cynogenmod這段免責聲明！

    /*
     * Your warranty is now void.
     * 您的產品保固已然作廢（因為刷機）！
     * I am not responsible for bricked devices, dead SD cards, thermonuclear war, or you getting fired because the alarm app failed.
     * 我對於手機變磚、儲存卡壞掉、核子戰爭，或是您因為鬧鈴app沒響而被炒魷魚，皆不負任何責任。
     * Please do some research if you have any concerns about features included in this ROM before flashing it!
     * 如果您對這個系統嵌有哪些特色功能有疑慮，請在刷機之前先做一些研究！
     * YOU are choosing to make these modifications, and if you point the finger at me for messing up your device, I will laugh at you.
     * 是您決定要做這些修改的（刷機），如果您指責我搞壞了您的設備，我會笑您。
     */

特別提到核子戰爭或被炒魷魚皆在免責範圍，帶來一些誇張的笑點。

我想大家要知道，**開源軟體若是無償取得，原則上就要有這樣的免責認知**，原來的作者主張在法律容許的最大範圍內主張不負擔保，畢竟，他們並沒有從後續使用者的利用行為，明著拿到任何的好處。

但如果是有償的提供、收費的服務呢？事實上，當軟體服務成為商品，它也必須符合各國對於電子消費產品、軟體客製化承攬的相關商法或專法的規範，也就是說，多數狀況下，收費的提供者必須依法去擔負，物之瑕疵或權利瑕疵相關的擔保責任。

也因為這樣，2004年後較新的開放源碼授權條款，也都在條款裡增加了「**軟體提供者自行提高擔保責任的彈性機制**」，例如，**Apache-2.0**裡的**Accepting Warranty or Additional Liability**，**GPL-3.0**裡的**Disclaiming warranty or limiting liability differently from the terms of sections 15 and 16 of this License**，**MPL-2.0**裡的**You may choose to offer, and to charge a fee for, warranty, support, indemnity or liability obligations to one or more recipients of Covered Software.**，以及**EPL-2.0**裡的**If that Commercial Contributor then makes performance claims, or offers warranties related to Product X, those performance claims and warranties are such Commercial Contributor's responsibility alone.**

所以，若是您無償取用開源軟體來進行商業服務，千萬不要再拘泥於它本來的免責聲明，認為自己並不需要對客戶負責，那個原則上已經不完全適用於您的商用情境；然返過來說，如果您是有償的取得開源軟體相關的服務，其實，您也是可以向您的開源軟體商務服務提供者，要求其必須要承擔軟體合用性及資安防護方面的擔保分配的。

這其實就是為何很多開源軟體也可以無償取得，但該產品的最後下游品牌商，還是要求中間的OEM/ODM或開發商，應該要取得該開源軟體EE(Enterprise Edition)等級付費授權的原因，因為EE關係下取得的軟體，它是帶著商業服務品質的擔保的，所以說，**如果中間開發商並不希望付費洽購處理，另一個變通模式，就是中間開發商自己提供更下游廠商，相關合用性和資安服務的擔保，來與下游品牌商取得共職。**