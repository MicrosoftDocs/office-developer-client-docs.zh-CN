---
title: 以编程方式设置地址列表的解析顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: f9559afb-8db1-ce72-3e11-9b3d47bb80b6
description: 上次修改时间：2012 年 7 月 6 日
ms.openlocfilehash: 4ca3e9d11a3133236d38ef31b01ecded932e8013
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345959"
---
# <a name="programmatically-set-the-resolution-order-for-address-lists"></a><span data-ttu-id="d86dc-103">以编程方式设置地址列表的解析顺序</span><span class="sxs-lookup"><span data-stu-id="d86dc-103">Programmatically set the resolution order for address lists</span></span>
  
<span data-ttu-id="d86dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d86dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d86dc-105">本主题包含一个 C++ 代码示例，该示例以编程方式设置解析电子邮件中的收件人和会议请求中的与会者的地址列表的顺序。</span><span class="sxs-lookup"><span data-stu-id="d86dc-105">This topic contains a code sample in C++ that programmatically sets the order of address lists by which recipients in email messages and attendees in meeting requests are resolved.</span></span>
  
<span data-ttu-id="d86dc-106">在 MAPI 中，每个配置文件可以支持多个地址列表，每个地址列表驻留在其自己的容器中。</span><span class="sxs-lookup"><span data-stu-id="d86dc-106">In MAPI, each profile can support multiple address lists and each address list resides in its own container.</span></span> <span data-ttu-id="d86dc-107">MAPI 支持接口中的 **[SetSearchPath](https://support.microsoft.com/kb/292590)** 方法，允许您在配置文件中设置用于名称解析的新搜索路径。</span><span class="sxs-lookup"><span data-stu-id="d86dc-107">MAPI supports the **[SetSearchPath](https://support.microsoft.com/kb/292590)** method in the interface that allows you to set a new search path in the profile that is used for name resolution.</span></span> <span data-ttu-id="d86dc-108">若要使用 **IAddrBook：：SetSearchPath** 方法，您必须在以所需顺序保存相关通讯簿容器的 **[SRowSet](srowset.md)** 数组中定义所需的解析顺序，然后将该数组指定为  *lpSearchPath*  参数。</span><span class="sxs-lookup"><span data-stu-id="d86dc-108">To use the **IAddrBook::SetSearchPath** method, you have to define the desired resolution order in a **[SRowSet](srowset.md)** array that holds the containers of the relevant address books in the desired order, and then specify the array as the  *lpSearchPath*  parameter.</span></span> <span data-ttu-id="d86dc-109">**SRowSet** 数组中每个条目的第一个属性必须是PR_ENTRYID通讯簿 **[](pidtagentryid-canonical-property.md)** 的 PR_ENTRYID 属性。</span><span class="sxs-lookup"><span data-stu-id="d86dc-109">The first property for each entry in the **SRowSet** array must be the **[PR_ENTRYID](pidtagentryid-canonical-property.md)** property of the corresponding address book.</span></span> 
  
<span data-ttu-id="d86dc-110">该代码示例在以下步骤中设置解析顺序：</span><span class="sxs-lookup"><span data-stu-id="d86dc-110">The code sample sets the resolution order in the following steps:</span></span>
  
1. <span data-ttu-id="d86dc-111">初始化要匹配的容器数，并指定数组中所需地址列表的名称和  `numANR` 解析  `ANROrder` 顺序。</span><span class="sxs-lookup"><span data-stu-id="d86dc-111">Initializes  `numANR` to the number of containers to match, and specifies the names and resolution order of the desired address lists in an  `ANROrder` array.</span></span> 
    
2. <span data-ttu-id="d86dc-112">使用 **MAPIInitialize** 函数初始化 MAPI。</span><span class="sxs-lookup"><span data-stu-id="d86dc-112">Initializes MAPI by using the **MAPIInitialize** function.</span></span> 
    
3.  <span data-ttu-id="d86dc-113">登录到 MAPI，并允许用户选择配置文件。</span><span class="sxs-lookup"><span data-stu-id="d86dc-113">Logs on to MAPI and allows the user to choose a profile.</span></span> 
    
4.  <span data-ttu-id="d86dc-114">获取当前会话中指向通讯簿的指针。</span><span class="sxs-lookup"><span data-stu-id="d86dc-114">Gets a pointer to the address book from the current session.</span></span> 
    
5. <span data-ttu-id="d86dc-115">打开通讯簿。</span><span class="sxs-lookup"><span data-stu-id="d86dc-115">Opens the Address Book.</span></span>
    
6. <span data-ttu-id="d86dc-116">打开根通讯簿的容器。</span><span class="sxs-lookup"><span data-stu-id="d86dc-116">Opens the container for the root Address Book.</span></span>
    
7. <span data-ttu-id="d86dc-117">打开根通讯簿容器的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="d86dc-117">Opens the hierarchy table of the root address book container.</span></span>
    
8. <span data-ttu-id="d86dc-118">获取层次结构中的通讯簿容器的列表。</span><span class="sxs-lookup"><span data-stu-id="d86dc-118">Gets the list of address book containers in the hierarchy.</span></span>
    
9. <span data-ttu-id="d86dc-119">通过将 所需的地址列表的名称与通讯簿层次结构中的现有名称进行比较，查找所需地址列表的条目  `ANROrder` ID。</span><span class="sxs-lookup"><span data-stu-id="d86dc-119">Looks for the entry IDs of the desired address lists by comparing the names of the desired address lists in  `ANROrder` to the existing names in the address book hierarchy.</span></span> 
    
10. <span data-ttu-id="d86dc-120">将相应的条目 ID 设置到 **SRowSet** 数组中  `pNewRows` 。</span><span class="sxs-lookup"><span data-stu-id="d86dc-120">Sets the appropriate entry IDs to the **SRowSet** array,  `pNewRows`.</span></span>
    
11. <span data-ttu-id="d86dc-121">调用并作为  `pNewRows`  *lpSearchPath*  参数传递给 **IAddrBook：：SetSearchPath** 以设置搜索路径。</span><span class="sxs-lookup"><span data-stu-id="d86dc-121">Calls and passes  `pNewRows` as the  *lpSearchPath*  parameter to **IAddrBook::SetSearchPath** to set the search path.</span></span> 
    
12. <span data-ttu-id="d86dc-122">清理内部缓冲区和指针。</span><span class="sxs-lookup"><span data-stu-id="d86dc-122">Cleans up internal buffers and pointers.</span></span>
    
13. <span data-ttu-id="d86dc-123">从 MAPI 注销。</span><span class="sxs-lookup"><span data-stu-id="d86dc-123">Logs off from MAPI.</span></span>
    
14. <span data-ttu-id="d86dc-124">未初始化 MAPI。</span><span class="sxs-lookup"><span data-stu-id="d86dc-124">Uninitalizes MAPI.</span></span>
    
<span data-ttu-id="d86dc-125">此代码示例使用默认安装中可用的地址列表 **Microsoft Office Outlook：所有** 联系人、所有 **组\*\*\*\*和联系人**。</span><span class="sxs-lookup"><span data-stu-id="d86dc-125">This code sample uses address lists that are available in the default installation of Microsoft Office Outlook: **All Contacts**, **All Groups**, and **Contacts**.</span></span> <span data-ttu-id="d86dc-126">启动并运行初始化的配置文件Outlook运行示例。</span><span class="sxs-lookup"><span data-stu-id="d86dc-126">You must run the sample after Outlook is started and is running on an initialized profile.</span></span> <span data-ttu-id="d86dc-127">该示例适用于使用一种语言 (例如，所有名称都使用英语) 。</span><span class="sxs-lookup"><span data-stu-id="d86dc-127">The sample works well with names that are in one language (for example, all names are in English).</span></span> <span data-ttu-id="d86dc-128">它不能用于多语言部署，例如，为运行非英语语言版本的用户本地化的"联系人"Outlook版本。</span><span class="sxs-lookup"><span data-stu-id="d86dc-128">It is not designed to work in multi-lingual deployments, for example the **Contacts** folder localized for a user running a non-English Outlook build.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="d86dc-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d86dc-129">See also</span></span>

- [<span data-ttu-id="d86dc-130">关于设置在 Outlook 中地址列表的解析顺序</span><span class="sxs-lookup"><span data-stu-id="d86dc-130">About Setting the Resolution Order for Address Lists in Outlook</span></span>](about-setting-the-resolution-order-for-address-lists-in-outlook.md)

