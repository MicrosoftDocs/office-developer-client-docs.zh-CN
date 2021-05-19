---
title: 当远程服务器位于缓存模式Outlook打开Exchange存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: cf01eab7-164d-c3b3-8bb0-9281e2119bc5
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 419c9ae734e8b58d0958970e7127b94d220b8382
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417817"
---
# <a name="open-a-store-on-the-remote-server-when-outlook-is-in-cached-exchange-mode"></a><span data-ttu-id="55532-103">当远程服务器位于缓存模式Outlook打开Exchange存储</span><span class="sxs-lookup"><span data-stu-id="55532-103">Open a store on the remote server when Outlook is in Cached Exchange Mode</span></span>

<span data-ttu-id="55532-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55532-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55532-105">本主题包含一个 C++ 代码示例，该示例演示如何在 Microsoft Outlook 2010 或 Microsoft Outlook 2013 位于缓存模式时，使用 **MDB_ONLINE** 标志打开远程Exchange存储。</span><span class="sxs-lookup"><span data-stu-id="55532-105">This topic contains a code sample in C++ that shows how to use the **MDB_ONLINE** flag to open a message store on the remote server when Microsoft Outlook 2010 or Microsoft Outlook 2013 is in Cached Exchange Mode.</span></span> 
  
<span data-ttu-id="55532-106">缓存 Exchange 模式允许 Outlook 2010 和 Outlook 2013 使用用户邮箱的本地副本，而 Outlook 2010 或 Outlook 2013 维护与远程 Exchange 服务器上用户邮箱的远程副本的联机连接。</span><span class="sxs-lookup"><span data-stu-id="55532-106">Cached Exchange Mode permits Outlook 2010 and Outlook 2013 to use a local copy of a user's mailbox while Outlook 2010 or Outlook 2013 maintains an online connection to a remote copy of the user's mailbox on the remote Exchange server.</span></span> <span data-ttu-id="55532-107">当 Outlook 2010 或 Outlook 2013 在缓存 Exchange 模式下运行时，默认情况下，登录到同一会话的任何 MAPI 解决方案也将连接到缓存的邮件存储。</span><span class="sxs-lookup"><span data-stu-id="55532-107">When Outlook 2010 or Outlook 2013 is running in Cached Exchange Mode, by default, any MAPI solutions that log on to the same session are also connected to the cached message store.</span></span> <span data-ttu-id="55532-108">访问的任何数据和对邮箱的本地副本进行的任何更改。</span><span class="sxs-lookup"><span data-stu-id="55532-108">Any data that is accessed and any changes that are made are made against the local copy of the mailbox.</span></span>
  
<span data-ttu-id="55532-109">客户端或服务提供商可以在调用 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md)时 **，在** *ulFlags* 参数中设置 MDB_ONLINE 的位，覆盖与本地邮件存储的连接，并打开远程服务器上存储。</span><span class="sxs-lookup"><span data-stu-id="55532-109">A client or service provider can override the connection to the local message store and open the store on the remote server by setting the bit for **MDB_ONLINE** in the  *ulFlags*  parameter when calling [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md).</span></span> <span data-ttu-id="55532-110">在远程服务器上成功打开该会话的存储区后，可以使用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 打开远程存储上的项目或文件夹。</span><span class="sxs-lookup"><span data-stu-id="55532-110">After the store has been successfully opened on the remote server for that session, you can use [IMAPISession::OpenEntry](imapisession-openentry.md) to open items or folders on the remote store.</span></span> 
  
<span data-ttu-id="55532-111">不能在同一 MAPI 会话中Exchange缓存模式和非缓存模式下同时打开缓存存储。</span><span class="sxs-lookup"><span data-stu-id="55532-111">You cannot open an Exchange store in cached mode and in non-cached mode at the same time in the same MAPI session.</span></span> <span data-ttu-id="55532-112">如果已经打开缓存的邮件存储区，或者必须使用此标记关闭存储，或打开新的 MAPI 会话，可以使用此标记在远程服务器上打开 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="55532-112">If you have already opened the cached message store, you must either close the store before you open it with this flag, or open a new MAPI session where you can open the Exchange store on the remote server by using this flag.</span></span>
  
<span data-ttu-id="55532-113">以下代码示例演示如何使用 *ulFlags* 参数中设置的 **MDB_ONLINE** 标志调用 **IMAPISession：：OpenMsgStore** 以打开远程服务器上的默认存储。</span><span class="sxs-lookup"><span data-stu-id="55532-113">The following code sample shows how to call **IMAPISession::OpenMsgStore** with the **MDB_ONLINE** flag set in the  *ulFlags*  parameter to open the default store on the remote server.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="55532-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55532-114">See also</span></span>

- [<span data-ttu-id="55532-115">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="55532-115">About MAPI Additions</span></span>](about-mapi-additions.md) 
- [<span data-ttu-id="55532-116">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="55532-116">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="55532-117">当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="55532-117">Access a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)

