---
title: 以编程方式设置地址列表的解决方案顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: f9559afb-8db1-ce72-3e11-9b3d47bb80b6
description: 上次修改时间： 2012 年 7 月 6 日
ms.openlocfilehash: 676d74c6441716203006f2db3e4a7d5777320a98
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775115"
---
# <a name="programmatically-set-the-resolution-order-for-address-lists"></a><span data-ttu-id="ce72d-103">以编程方式设置地址列表的解决方案顺序</span><span class="sxs-lookup"><span data-stu-id="ce72d-103">Programmatically set the resolution order for address lists</span></span>
  
<span data-ttu-id="ce72d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ce72d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ce72d-105">本主题包含在以编程方式设置消息和会议请求中的与会者都已解析通过电子邮件中的收件人的地址列表的顺序的 c + + 代码示例。</span><span class="sxs-lookup"><span data-stu-id="ce72d-105">This topic contains a code sample in C++ that programmatically sets the order of address lists by which recipients in email messages and attendees in meeting requests are resolved.</span></span>
  
<span data-ttu-id="ce72d-106">MAPI 中, 每个配置文件可以支持多个地址列表和每个地址列表位于其自己的容器。</span><span class="sxs-lookup"><span data-stu-id="ce72d-106">In MAPI, each profile can support multiple address lists and each address list resides in its own container.</span></span> <span data-ttu-id="ce72d-107">MAPI 中，您可以用于名称解析配置文件中设置新的搜索路径的接口支持**[SetSearchPath](http://support.microsoft.com/kb/292590)** 方法。</span><span class="sxs-lookup"><span data-stu-id="ce72d-107">MAPI supports the **[SetSearchPath](http://support.microsoft.com/kb/292590)** method in the interface that allows you to set a new search path in the profile that is used for name resolution.</span></span> <span data-ttu-id="ce72d-108">若要使用的**IAddrBook::SetSearchPath**方法，您必须按所需的顺序，包含相关的通讯簿容器**[SRowSet](srowset.md)** 数组中定义所需要的分辨率顺序，然后将该数组指定为*lpSearchPath* 参数。</span><span class="sxs-lookup"><span data-stu-id="ce72d-108">To use the **IAddrBook::SetSearchPath** method, you have to define the desired resolution order in a **[SRowSet](srowset.md)** array that holds the containers of the relevant address books in the desired order, and then specify the array as the  *lpSearchPath*  parameter.</span></span> <span data-ttu-id="ce72d-109">为每个项**SRowSet**数组中的第一个属性必须是相应的通讯簿的**[PR_ENTRYID](pidtagentryid-canonical-property.md)** 属性。</span><span class="sxs-lookup"><span data-stu-id="ce72d-109">The first property for each entry in the **SRowSet** array must be the **[PR_ENTRYID](pidtagentryid-canonical-property.md)** property of the corresponding address book.</span></span> 
  
<span data-ttu-id="ce72d-110">代码示例设置解析顺序执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ce72d-110">The code sample sets the resolution order in the following steps:</span></span>
  
1. <span data-ttu-id="ce72d-111">初始化`numANR`的容器，若要匹配，数，并指定的名称和解决方案中的所需的地址列表中的顺序`ANROrder`数组。</span><span class="sxs-lookup"><span data-stu-id="ce72d-111">Initializes  `numANR` to the number of containers to match, and specifies the names and resolution order of the desired address lists in an  `ANROrder` array.</span></span> 
    
2. <span data-ttu-id="ce72d-112">使用**MAPIInitialize**函数初始化 MAPI。</span><span class="sxs-lookup"><span data-stu-id="ce72d-112">Initializes MAPI by using the **MAPIInitialize** function.</span></span> 
    
3.  <span data-ttu-id="ce72d-113">登录到 MAPI，并允许用户选择一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="ce72d-113">Logs on to MAPI and allows the user to choose a profile.</span></span> 
    
4.  <span data-ttu-id="ce72d-114">从当前会话中获取对通讯簿的指针。</span><span class="sxs-lookup"><span data-stu-id="ce72d-114">Gets a pointer to the address book from the current session.</span></span> 
    
5. <span data-ttu-id="ce72d-115">打开通讯簿。</span><span class="sxs-lookup"><span data-stu-id="ce72d-115">Opens the Address Book.</span></span>
    
6. <span data-ttu-id="ce72d-116">打开根通讯簿的容器。</span><span class="sxs-lookup"><span data-stu-id="ce72d-116">Opens the container for the root Address Book.</span></span>
    
7. <span data-ttu-id="ce72d-117">打开根通讯簿容器层次结构的表。</span><span class="sxs-lookup"><span data-stu-id="ce72d-117">Opens the hierarchy table of the root address book container.</span></span>
    
8. <span data-ttu-id="ce72d-118">获取列表地址簿容器层次结构中。</span><span class="sxs-lookup"><span data-stu-id="ce72d-118">Gets the list of address book containers in the hierarchy.</span></span>
    
9. <span data-ttu-id="ce72d-119">通过比较名称中的所需的地址列表的查找所需的地址列表的条目 Id`ANROrder`到通讯簿层次结构中现有的名称。</span><span class="sxs-lookup"><span data-stu-id="ce72d-119">Looks for the entry IDs of the desired address lists by comparing the names of the desired address lists in  `ANROrder` to the existing names in the address book hierarchy.</span></span> 
    
10. <span data-ttu-id="ce72d-120">将相应的条目 Id 设置为**SRowSet**数组， `pNewRows`。</span><span class="sxs-lookup"><span data-stu-id="ce72d-120">Sets the appropriate entry IDs to the **SRowSet** array,  `pNewRows`.</span></span>
    
11. <span data-ttu-id="ce72d-121">调用，并传递`pNewRows`作为**IAddrBook::SetSearchPath**设置的搜索路径*lpSearchPath*参数。</span><span class="sxs-lookup"><span data-stu-id="ce72d-121">Calls and passes  `pNewRows` as the  *lpSearchPath*  parameter to **IAddrBook::SetSearchPath** to set the search path.</span></span> 
    
12. <span data-ttu-id="ce72d-122">清理内部缓冲区和指针。</span><span class="sxs-lookup"><span data-stu-id="ce72d-122">Cleans up internal buffers and pointers.</span></span>
    
13. <span data-ttu-id="ce72d-123">MAPI 关闭日志。</span><span class="sxs-lookup"><span data-stu-id="ce72d-123">Logs off from MAPI.</span></span>
    
14. <span data-ttu-id="ce72d-124">Uninitalizes MAPI。</span><span class="sxs-lookup"><span data-stu-id="ce72d-124">Uninitalizes MAPI.</span></span>
    
<span data-ttu-id="ce72d-125">本代码示例使用默认安装的 Microsoft Office Outlook 中可用的地址列表：**所有联系人**、**所有组**和**联系人**。</span><span class="sxs-lookup"><span data-stu-id="ce72d-125">This code sample uses address lists that are available in the default installation of Microsoft Office Outlook: **All Contacts**, **All Groups**, and **Contacts**.</span></span> <span data-ttu-id="ce72d-126">Outlook 启动并运行已初始化的配置文件后，您必须运行示例。</span><span class="sxs-lookup"><span data-stu-id="ce72d-126">You must run the sample after Outlook is started and is running on an initialized profile.</span></span> <span data-ttu-id="ce72d-127">该示例适用于一种语言中的名称 （例如，所有名称都均为英语）。</span><span class="sxs-lookup"><span data-stu-id="ce72d-127">The sample works well with names that are in one language (for example, all names are in English).</span></span> <span data-ttu-id="ce72d-128">它不是以在多语言部署中，例如**联系人**文件夹本地化运行非英语 Outlook 生成的用户。</span><span class="sxs-lookup"><span data-stu-id="ce72d-128">It is not designed to work in multi-lingual deployments, for example the **Contacts** folder localized for a user running a non-English Outlook build.</span></span> 
  
```cpp
#include "stdafx.h" 
#include <mapix.h> 
#include <mapiguid.h> 
#include <mapiutil.h> 
#include <mapidefs.h> 
#include <stdio.h> 
#include <conio.h> 
 
//Number of address lists to resolve against 
const int numANR = 3; 
WCHAR *ANROrder[numANR] = {_T("All Contacts"), _T("All Groups"), _T("Contacts")}; 
UINT  numContainersFound [numANR] = {0}; 
 
// Temporary structure to allocate buffer in MAPI. This will be used as a parent buffer to free space later. 
LPVOID tempLink; 
 
// Forward declaration of helper function to copy binary data 
STDMETHODIMP CopySBinary( 
    LPSBinary psbDest, 
    const LPSBinary psbSrc, 
    LPVOID pParent); 
 
void main() 
{ 
    // MAPI address book and session variables 
    HRESULT       hRes = S_OK;            // Result code returned from MAPI calls. 
    LPMAPISESSION lpSession = NULL;   // Pointer to MAPI session. 
    LPADRBOOK     lpAddrBook = NULL;  // Pointer to Address Book. 
 
    // Counters 
    ULONG         i = 0;                  // Index counter 
    ULONG         j = 0;                  // Index counter 
 
    // Used for querying hierarchy 
    ULONG                                   ulObjType = 0L;      // Object type returned by MAPI 
    LPMAPICONTAINER     pIABRoot = NULL;     // Root address book container 
    LPMAPITABLE              pHTable = NULL;      // Holds hierarchy table 
    LPSRowSet        pRows = NULL;        // Pointer to row set. Stores AB Address Lists 
 
    // Used for setting search path 
    LPSRowSet     pNewRows = NULL;        // Pointer to new row set 
    SizedSRowSet  (numANR, NewRows);      // New row set 
    SPropValue    sProps[numANR] = {0};   // Property tag structure 
 
    // Structures contaning MAPI Column Sets required for querying tables 
    enum { 
        abPR_ENTRYID, 
        abPR_DISPLAY_NAME_W, 
        abNUM_COLS}; 
 
    static SizedSPropTagArray(abNUM_COLS,abCols) = { 
        abNUM_COLS, 
        PR_ENTRYID, 
        PR_DISPLAY_NAME_W, 
    }; 
 
    // Initialize MAPI 
    if (FAILED ( hRes = MAPIInitialize(NULL))) goto Exit; 
 
    // Log on to MAPI and allow user to choose profile 
 
    // Note: This uses the current MAPI session if there is one 
    if (FAILED ( hRes = MAPILogonEx(NULL, NULL, NULL, MAPI_LOGON_UI, &lpSession))) goto Exit; 
 
    // Open the Address Book 
    if (FAILED (hRes = lpSession->OpenAddressBook(NULL, NULL, NULL, &lpAddrBook))) goto Cleanup; 
 
    // Open the Address Book Root container 
    if (FAILED (hRes = lpAddrBook -> OpenEntry ( 
        0L,  
        NULL, 
        NULL,  
        0L, 
        &ulObjType, 
        (LPUNKNOWN *) &pIABRoot ))) 
    goto Cleanup; 
 
    // Intentionally allocate 0 bytes. This is used for buffer management. 
    MAPIAllocateBuffer(0L, &tempLink);  
 
    // Make sure there is a Container object 
    // Query hierarchy for containers 
    if ( MAPI_ABCONT == ulObjType ) { 
        // - Call IMAPIContainer::GetHierarchyTable to open the Hierarchy 
        //   table of the root address book container 
        if ( FAILED ( hRes = pIABRoot -> GetHierarchyTable ( CONVENIENT_DEPTH | MAPI_UNICODE, 
            &pHTable ) ) ) 
        goto Cleanup; 
 
        // Get the list of address book containers first 
        if ( FAILED ( hRes = HrQueryAllRows (  
            pHTable, 
            (LPSPropTagArray) &abCols, 
            NULL, 
            NULL, 
            0L, 
            &pRows ) ) ) 
        goto Cleanup; 
 
        // Initialize the structures to set the search order 
        ZeroMemory(&NewRows, numANR * sizeof(SRow)); 
        pNewRows = (LPSRowSet)&NewRows; 
 
        // Set the number of rows you are going to set 
        pNewRows->cRows = numANR; 
 
        // Set the pointers to the structures 
        for (i=0; i<numANR; i++) 
            pNewRows->aRow[i].lpProps = &sProps[i]; 
 
        // Compare the list to the ones that of interest 
        for (i=0; i<pRows->cRows; i++) { 
            if (pRows->aRow[i].lpProps[abPR_DISPLAY_NAME_W].ulPropTag == PR_DISPLAY_NAME_W) { 
                LPWSTR containerName =  pRows->aRow[i].lpProps[abPR_DISPLAY_NAME_W].Value.lpszW; 
                for (j=0; j<numANR; j++) 
                    if (!wcscmp (containerName, ANROrder[j])) { 
                        // First check if a container with this name has been found already 
                        if (numContainersFound[j] == 0) { 
                            numContainersFound[j]++; 
                            pNewRows->aRow[j].cValues = 1; 
 
                            // The property being passing is PR_ENTRY_ID 
                            pNewRows->aRow[j].lpProps[0].ulPropTag = PR_ENTRYID; 
 
                            // Copy the binary data over 
                            if (FAILED (hRes = CopySBinary( 
                                &pNewRows->aRow[j].lpProps[0].Value.bin, 
                                &pRows->aRow[i].lpProps[abPR_ENTRYID].Value.bin, 
                                tempLink))) {  
                                    printf ("Fatal Error:Failed to copy entry IDs\n"); 
                                    goto Cleanup; 
                            } 
                         } 
                         // More than 1 container matched the same name 
                         else {  
                             printf ("Fatal Error: Duplicate container found, container name = %s\n", containerName); 
                             goto Cleanup; 
                         } 
                    } 
            } 
        } 
 
        // Only set the search path if all the rows have been found 
        // Check the array for any entries that were blank 
        for (i=0; i< numANR; i++) 
            if (numContainersFound [i] == 0) { 
                printf ("Fatal Error: all containers were not found\n"); 
                goto Cleanup; 
            } 
 
        // Everything is safe to set the search path now 
        if (FAILED (hRes = lpAddrBook->SetSearchPath(0, pNewRows))) {                    
            printf ("Fatal Error: failed to set the search path\n"); 
            goto Cleanup; 
        } 
    } 
 
    Cleanup: 
        MAPIFreeBuffer(tempLink); 
        UlRelease(pHTable); 
        FreeProws(pRows); 
        UlRelease (pIABRoot); 
        UlRelease(lpAddrBook); 
 
        // Log off from MAPI 
        hRes = lpSession->Logoff(NULL, NULL, 0); 
        UlRelease(lpSession); 
 
    Exit: 
        // Uninitialize MAPI 
        MAPIUninitialize(); 
} 
 
///////////////////////////////////////////////////////////// 
//    CopySBinary() 
// 
//    Parameters 
// 
//    Purpose 
//      Allocates a new SBinary and copies psbSrc into it 
// 
 
STDMETHODIMP CopySBinary( 
    LPSBinary psbDest, 
    const LPSBinary psbSrc, 
    LPVOID pParent) 
{ 
    HRESULT     hRes = S_OK; 
    psbDest->cb = psbSrc->cb; 
 
    if (psbSrc->cb) { 
        if (pParent) 
            hRes = MAPIAllocateMore( 
                 psbSrc->cb, 
                 pParent, 
                 (LPVOID*) &psbDest->lpb); 
        else 
            hRes = MAPIAllocateBuffer( 
                 psbSrc->cb, 
                 (LPVOID*) &psbDest->lpb); 
 
    if (!FAILED(hRes)) 
        CopyMemory(psbDest->lpb,psbSrc->lpb,psbSrc->cb); 
    } 
 
   return hRes; 
} 

```

## <a name="see-also"></a><span data-ttu-id="ce72d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce72d-129">See also</span></span>

- [<span data-ttu-id="ce72d-130">关于在 Outlook 中设置地址列表的解析顺序</span><span class="sxs-lookup"><span data-stu-id="ce72d-130">About Setting the Resolution Order for Address Lists in Outlook</span></span>](about-setting-the-resolution-order-for-address-lists-in-outlook.md)

