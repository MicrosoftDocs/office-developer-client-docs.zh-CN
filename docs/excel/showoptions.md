---
title: ShowOptions
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 51acac58-ec39-488f-979c-1887dc2ab94b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5b58b71dc4f2441448eb3e0dac2c3c5763675927
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407695"
---
# <a name="showoptions"></a><span data-ttu-id="a8530-103">ShowOptions</span><span class="sxs-lookup"><span data-stu-id="a8530-103">ShowOptions</span></span>

<span data-ttu-id="a8530-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a8530-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a8530-105">显示从用户收集信息的模式对话框。</span><span class="sxs-lookup"><span data-stu-id="a8530-105">Shows a modal dialog box to collect information from the user.</span></span> <span data-ttu-id="a8530-106">当用户单击"公式"部分下"高级"类别中 **" ("Excel** 选项"对话框中所选群集连接器的"群集类型"框旁边的"选项"按钮时，) 将调用此入口点。  </span><span class="sxs-lookup"><span data-stu-id="a8530-106">This entry point is called when a user clicks the **Options** button next to the **Cluster type** box for the selected cluster connector in the **Excel Options** dialog box (in the **Advanced** category under the **Formulas** section).</span></span> <span data-ttu-id="a8530-107">群集连接器负责实现自己的选项对话框接口，以及将相关的数据存储在注册表或其他地方。</span><span class="sxs-lookup"><span data-stu-id="a8530-107">Cluster connectors are responsible for implementing their own options dialog interface and for storing the related data in the registry or elsewhere.</span></span> <span data-ttu-id="a8530-108">选项在群集连接器内部。</span><span class="sxs-lookup"><span data-stu-id="a8530-108">The options are internal to the cluster connector.</span></span> <span data-ttu-id="a8530-109">Excel他们。</span><span class="sxs-lookup"><span data-stu-id="a8530-109">Excel is not aware of them.</span></span> 
  
```cpp
int ShowOptions(HWND hWndParent)
```

## <a name="parameters"></a><span data-ttu-id="a8530-110">参数</span><span class="sxs-lookup"><span data-stu-id="a8530-110">Parameters</span></span>

<span data-ttu-id="a8530-111">_hWndParent_</span><span class="sxs-lookup"><span data-stu-id="a8530-111">_hWndParent_</span></span>
  
> <span data-ttu-id="a8530-112">窗口的Excel句柄。</span><span class="sxs-lookup"><span data-stu-id="a8530-112">A handle to the Excel window.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a8530-113">返回值</span><span class="sxs-lookup"><span data-stu-id="a8530-113">Return value</span></span>

<span data-ttu-id="a8530-114">**xlHpcRetSuccess（** 如果显示对话框）; **xlHpcRetCallFailed（** 如果未显示）。</span><span class="sxs-lookup"><span data-stu-id="a8530-114">**xlHpcRetSuccess** if the dialog box was shown; **xlHpcRetCallFailed** if it was not shown.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a8530-115">备注</span><span class="sxs-lookup"><span data-stu-id="a8530-115">Remarks</span></span>

<span data-ttu-id="a8530-116">群集连接器可以使用此对话框从用户获取信息，例如要使用哪些群集服务器。</span><span class="sxs-lookup"><span data-stu-id="a8530-116">Cluster connectors can use this dialog box to get information, such as what cluster server to use, from the user.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a8530-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8530-117">See also</span></span>

- [<span data-ttu-id="a8530-118">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="a8530-118">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

