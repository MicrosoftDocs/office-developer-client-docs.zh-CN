---
title: Append 方法 (ADOX Views)
TOCTitle: Append Method (ADOX Views)
ms:assetid: 202f1d0a-dc5d-84e5-daf3-3212e5bc6088
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248985(v=office.15)
ms:contentKeyID: 48543655
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 106dd9d72cb350422f00da05859bc096cb2b52e9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467261"
---
# <a name="append-method-adox-views"></a><span data-ttu-id="b9653-102">Append 方法 (ADOX Views)</span><span class="sxs-lookup"><span data-stu-id="b9653-102">Append Method (ADOX Views)</span></span>


<span data-ttu-id="b9653-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b9653-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="b9653-104">创建一个新的 [View](view-object-adox.md) 对象，并将其追加到 [Views](views-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="b9653-104">Creates a new [View](view-object-adox.md) object and appends it to the [Views](views-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9653-105">语法</span><span class="sxs-lookup"><span data-stu-id="b9653-105">Syntax</span></span>

<span data-ttu-id="b9653-106">*视图*。追加*名称*，*命令*</span><span class="sxs-lookup"><span data-stu-id="b9653-106">*Views*.Append*Name*, *Command*</span></span>

## <a name="parameters"></a><span data-ttu-id="b9653-107">参数</span><span class="sxs-lookup"><span data-stu-id="b9653-107">Parameters</span></span>

  - <span data-ttu-id="b9653-108">*Name*</span><span class="sxs-lookup"><span data-stu-id="b9653-108">*Name*</span></span>

  - <span data-ttu-id="b9653-109">**String** 值，指定要创建的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="b9653-109">A **String** value that specifies the name of the view to create.</span></span>

  - <span data-ttu-id="b9653-110">*Command*</span><span class="sxs-lookup"><span data-stu-id="b9653-110">*Command*</span></span>

  - <span data-ttu-id="b9653-111">一个表示要创建的视图的 ADO [Command](command-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="b9653-111">An ADO [Command](command-object-ado.md) object that represents the view to create.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9653-112">备注</span><span class="sxs-lookup"><span data-stu-id="b9653-112">Remarks</span></span>

<span data-ttu-id="b9653-113">使用在 **Command** 对象中指定的名称和属性在数据源中创建一个新视图。</span><span class="sxs-lookup"><span data-stu-id="b9653-113">Creates a new view in the data source with the name and attributes specified in the **Command** object.</span></span>

<span data-ttu-id="b9653-p101">如果用户指定的命令文本表示过程而非视图，则其行为取决于提供程序。如果该提供程序不支持保留命令，则 **Append** 将失败。</span><span class="sxs-lookup"><span data-stu-id="b9653-p101">If the command text that the user specifies represents a procedure rather than a view, the behavior is dependent upon the provider. **Append** will fail if the provider does not support persisting commands.</span></span>


> [!NOTE]
> <P><span data-ttu-id="b9653-116">使用 Microsoft Jet OLE DB 提供程序，将允许<STRONG>Views</STRONG>集合的<STRONG>Append</STRONG>方法，您可以在<EM>命令</EM>参数中指定<STRONG>过程</STRONG>而不是<STRONG>视图</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="b9653-116">When using the OLE DB Provider for Microsoft Jet, the <STRONG>Views</STRONG> collection <STRONG>Append</STRONG> method will allow you to specify a <STRONG>Procedure</STRONG> rather than a <STRONG>View</STRONG> in the <EM>Command</EM> parameter.</span></span> <span data-ttu-id="b9653-117">该 <STRONG>Procedure</STRONG> 将添加到数据源，并将添加到 <STRONG>Views</STRONG> 集合。</span><span class="sxs-lookup"><span data-stu-id="b9653-117">The <STRONG>Procedure</STRONG> will be added to the data source and will be added to the <STRONG>Views</STRONG> collection.</span></span> <span data-ttu-id="b9653-118">执行 <STRONG>Append</STRONG> 之后，如果刷新 <STRONG>Procedures</STRONG> 和 <STRONG>Views</STRONG> 集合，可以看到该 <STRONG>Procedure</STRONG> 不再位于 <STRONG>Views</STRONG> 集合中，而是出现在 <STRONG>Procedures</STRONG> 集合中。</span><span class="sxs-lookup"><span data-stu-id="b9653-118">After the <STRONG>Append</STRONG>, if the <STRONG>Procedures</STRONG> and <STRONG>Views</STRONG> collections are refreshed, the <STRONG>Procedure</STRONG> will no longer be in the <STRONG>Views</STRONG> collection and will appear in the <STRONG>Procedures</STRONG> collection.</span></span></P>


