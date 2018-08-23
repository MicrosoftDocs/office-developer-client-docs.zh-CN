---
title: Outlook 时在缓存 Exchange 模式下打开存储在远程服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: cf01eab7-164d-c3b3-8bb0-9281e2119bc5
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 7c1b3d3d5eed6bc991f8e4fd702fa197d610c104
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584798"
---
# <a name="open-a-store-on-the-remote-server-when-outlook-is-in-cached-exchange-mode"></a><span data-ttu-id="81e70-103">Outlook 时在缓存 Exchange 模式下打开存储在远程服务器</span><span class="sxs-lookup"><span data-stu-id="81e70-103">Open a store on the remote server when Outlook is in Cached Exchange Mode</span></span>

<span data-ttu-id="81e70-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81e70-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="81e70-105">本主题包含演示如何使用**MDB_ONLINE**标志远程服务器上的消息存储时打开 Microsoft Outlook 2010 或 Microsoft Outlook 2013 缓存 Exchange 模式下的 c + + 中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="81e70-105">This topic contains a code sample in C++ that shows how to use the **MDB_ONLINE** flag to open a message store on the remote server when Microsoft Outlook 2010 or Microsoft Outlook 2013 is in Cached Exchange Mode.</span></span> 
  
<span data-ttu-id="81e70-106">缓存的 Exchange 模式允许 Outlook 2010 和 Outlook 2013 以使用用户的邮箱的本地副本，而 Outlook 2010 或 Outlook 2013 保持联机连接到的远程副本的远程 Exchange 服务器上的用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="81e70-106">Cached Exchange Mode permits Outlook 2010 and Outlook 2013 to use a local copy of a user's mailbox while Outlook 2010 or Outlook 2013 maintains an online connection to a remote copy of the user's mailbox on the remote Exchange server.</span></span> <span data-ttu-id="81e70-107">在 Outlook 2010 或 Outlook 2013 中运行时缓存 Exchange 模式，默认情况下，登录到同一个会话任何 MAPI 解决方案还会连接到缓存的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="81e70-107">When Outlook 2010 or Outlook 2013 is running in Cached Exchange Mode, by default, any MAPI solutions that log on to the same session are also connected to the cached message store.</span></span> <span data-ttu-id="81e70-108">对邮箱的本地副本进行访问的任何数据和所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="81e70-108">Any data that is accessed and any changes that are made are made against the local copy of the mailbox.</span></span>
  
<span data-ttu-id="81e70-109">客户端或服务提供程序可以重写与本地消息存储库的连接，并打开远程服务器上的存储通过调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)时为**MDB_ONLINE** *ulFlags*参数中设置了位。</span><span class="sxs-lookup"><span data-stu-id="81e70-109">A client or service provider can override the connection to the local message store and open the store on the remote server by setting the bit for **MDB_ONLINE** in the  *ulFlags*  parameter when calling [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md).</span></span> <span data-ttu-id="81e70-110">存储已成功打开远程服务器上为该会话后，您可以使用[IMAPISession::OpenEntry](imapisession-openentry.md)打开项目或对远程存储的文件夹。</span><span class="sxs-lookup"><span data-stu-id="81e70-110">After the store has been successfully opened on the remote server for that session, you can use [IMAPISession::OpenEntry](imapisession-openentry.md) to open items or folders on the remote store.</span></span> 
  
<span data-ttu-id="81e70-111">在缓存模式和非缓存模式下在同一 MAPI 会话中的同一时间，您无法打开 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="81e70-111">You cannot open an Exchange store in cached mode and in non-cached mode at the same time in the same MAPI session.</span></span> <span data-ttu-id="81e70-112">如果您已经打开的缓存的消息存储之前，必须也关闭存储打开与此标志，或打开新其中可以使用此标志打开 Exchange 存储的远程服务器上的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="81e70-112">If you have already opened the cached message store, you must either close the store before you open it with this flag, or open a new MAPI session where you can open the Exchange store on the remote server by using this flag.</span></span>
  
<span data-ttu-id="81e70-113">下面的代码示例演示如何使用*ulFlags*参数中的设置以打开远程服务器上的默认存储**MDB_ONLINE**标志调用**IMAPISession::OpenMsgStore** 。</span><span class="sxs-lookup"><span data-stu-id="81e70-113">The following code sample shows how to call **IMAPISession::OpenMsgStore** with the **MDB_ONLINE** flag set in the  *ulFlags*  parameter to open the default store on the remote server.</span></span> 
  
```cpp
HRESULT HrRemoteMessageStore( 
    LPMAPISESSION lpMAPISession, 
    LPMDB* lppMDB) 
{ 
    HRESULT hRes = S_OK; 
    LPMAPITABLE pStoresTbl = NULL; 
    SRestriction sres = {0}; 
    SPropValue spv = {0}; 
    LPSRowSet pRow = NULL; 
    LPMDB lpTempMDB = NULL; 
    enum {EID,NUM_COLS}; 
    static SizedSPropTagArray(NUM_COLS,sptCols) = {NUM_COLS, 
        PR_ENTRYID, 
    }; 
 
    //Obtain the table of all the message stores that are available 
    hRes = lpMAPISession-&gt;GetMsgStoresTable(0, &amp;pStoresTbl); 
     
    if (SUCCEEDED(hRes) &amp;&amp; pStoresTbl) 
    { 
        //Set up restrictions for the default store 
        sres.rt = RES_PROPERTY;                                  //Comparing a property 
        sres.res.resProperty.relop = RELOP_EQ;                   //Testing equality 
        sres.res.resProperty.ulPropTag = PR_DEFAULT_STORE;       //Tag to compare 
        sres.res.resProperty.lpProp = &amp;spv;                      //Prop tag and value to compare against 
     
        spv.ulPropTag = PR_DEFAULT_STORE;                        //Tag type 
        spv.Value.b   = TRUE;                                    //Tag value 
     
        //Convert the table to an array that can be stepped through 
        //Only one message store should have PR_DEFAULT_STORE set to true, so that only one will be returned 
        hRes = HrQueryAllRows( 
            pStoresTbl,                                          //Table to query 
            (LPSPropTagArray) &amp;sptCols,                          //Which columns to obtain 
            &amp;sres,                                               //Restriction to use 
            NULL,                                                //No sort order 
            0,                                                   //Max number of rows (0 means no limit) 
            &amp;pRow);                                              //Array to return 
 
        if (SUCCEEDED(hRes) &amp;&amp; pRow &amp;&amp; pRow-&gt;cRows) 
        {     
            //Open the first returned (default) message store 
            hRes = lpMAPISession-&gt;OpenMsgStore( 
                NULL,                                                //Window handle for dialogs 
                pRow-&gt;aRow[0].lpProps[EID].Value.bin.cb,             //size and... 
                (LPENTRYID)pRow-&gt;aRow[0].lpProps[EID].Value.bin.lpb, //value of entry to open 
                NULL,                                                //Use default interface (IMsgStore) to open store 
                MAPI_BEST_ACCESS | MDB_ONLINE,                       //Flags 
                &amp;lpTempMDB);                                         //Pointer to put the store in 
            if (SUCCEEDED(hRes) &amp;&amp; lppMDB) lppMDB* = lpTempMDB; 
        } 
    } 
    FreeProws(pRow); 
    if (pStoresTbl) pStoresTbl-&gt;Release(); 
 
    return hRes; 
}

```

## <a name="see-also"></a><span data-ttu-id="81e70-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81e70-114">See also</span></span>

- [<span data-ttu-id="81e70-115">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="81e70-115">About MAPI Additions</span></span>](about-mapi-additions.md) 
- [<span data-ttu-id="81e70-116">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="81e70-116">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="81e70-117">当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="81e70-117">Access a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)

