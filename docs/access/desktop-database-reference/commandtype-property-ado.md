---
<span data-ttu-id="15a6f-101"><<<<<<< 标头标题： CommandType 属性 (ADO) TOCTitle: CommandType 属性 (ADO) === 标题： CommandType 属性 (ADO) TOCTitle: CommandType 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="15a6f-101"><<<<<<< HEAD title: CommandType Property (ADO) TOCTitle: CommandType Property (ADO) ======= title: CommandType property (ADO) TOCTitle: CommandType property (ADO)</span></span>
>>>>>>> <span data-ttu-id="15a6f-102">母版页 ms:assetid: c8d4fc1c-502b-11f3-af9d-605a03b6f056 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249976(v=office.15) ms:contentKeyID: 48547663 ms.date: 09/18/2015 mtps_version: office.15.aspx f1_keywords:</span><span class="sxs-lookup"><span data-stu-id="15a6f-102">master ms:assetid: c8d4fc1c-502b-11f3-af9d-605a03b6f056 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249976(v=office.15) ms:contentKeyID: 48547663 ms.date: 09/18/2015 mtps_version: v=office.15 f1_keywords:</span></span>
- <span data-ttu-id="15a6f-103">ado210.chm1231125 f1_categories:</span><span class="sxs-lookup"><span data-stu-id="15a6f-103">ado210.chm1231125 f1_categories:</span></span>
- <span data-ttu-id="15a6f-104">Office.Version=v15</span><span class="sxs-lookup"><span data-stu-id="15a6f-104">Office.Version=v15</span></span>
---

<span data-ttu-id="15a6f-105"><<<<<<< 头</span><span class="sxs-lookup"><span data-stu-id="15a6f-105"><<<<<<< HEAD</span></span>
# <a name="commandtype-property-ado"></a><span data-ttu-id="15a6f-106">CommandType 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="15a6f-106">CommandType Property (ADO)</span></span>
=======
# <a name="commandtype-property-ado"></a><span data-ttu-id="15a6f-107">CommandType 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="15a6f-107">CommandType property (ADO)</span></span>
>>>>>>> <span data-ttu-id="15a6f-108">母版</span><span class="sxs-lookup"><span data-stu-id="15a6f-108">master</span></span>


<span data-ttu-id="15a6f-109">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="15a6f-109">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="15a6f-110">指示 [Command](command-object-ado.md) 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="15a6f-110">Indicates the type of a [Command](command-object-ado.md) object.</span></span>

<span data-ttu-id="15a6f-111"><<<<<<< 头</span><span class="sxs-lookup"><span data-stu-id="15a6f-111"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="15a6f-112">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="15a6f-112">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="15a6f-113">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="15a6f-113">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="15a6f-114">母版</span><span class="sxs-lookup"><span data-stu-id="15a6f-114">master</span></span>

<span data-ttu-id="15a6f-115">设置或返回一个或多个 [CommandTypeEnum](commandtypeenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="15a6f-115">Sets or returns one or more [CommandTypeEnum](commandtypeenum.md) values.</span></span>

> [!NOTE]
> <span data-ttu-id="15a6f-p101">[!注释] 不要将 **adCmdFile** 或 **adCmdTableDirect** 的 **CommandTypeEnum** 值与 **CommandType** 一起使用。这些值仅可作为 [Recordset](open-method-ado-recordset.md) 的 [Open](requery-method-ado.md) 和 [Requery](recordset-object-ado.md) 方法的选项使用。</span><span class="sxs-lookup"><span data-stu-id="15a6f-p101">Do not use the **CommandTypeEnum** values of **adCmdFile** or **adCmdTableDirect** with **CommandType**. These values can only be used as options with the [Open](open-method-ado-recordset.md) and [Requery](requery-method-ado.md) methods of a [Recordset](recordset-object-ado.md).</span></span>


## <a name="remarks"></a><span data-ttu-id="15a6f-118">备注</span><span class="sxs-lookup"><span data-stu-id="15a6f-118">Remarks</span></span>

<span data-ttu-id="15a6f-119">使用 **CommandType** 属性可以优化 [CommandText](commandtext-property-ado.md) 属性的求值过程。</span><span class="sxs-lookup"><span data-stu-id="15a6f-119">Use the **CommandType** property to optimize evaluation of the [CommandText](commandtext-property-ado.md) property.</span></span>

<span data-ttu-id="15a6f-120"><<<<<<< 标头如果**CommandType**属性值等于**adCmdUnknown** （默认值），因为 ADO 必须进行到提供程序的调用，以确定是否满足以下条件，您可能会遇到性能降低的**CommandText**属性是 SQL 语句、 存储的过程或表名。</span><span class="sxs-lookup"><span data-stu-id="15a6f-120"><<<<<<< HEAD If the **CommandType** property value equals **adCmdUnknown** (the default value), you may experience diminished performance because ADO must make calls to the provider to determine if the **CommandText** property is an SQL statement, a stored procedure, or a table name.</span></span> <span data-ttu-id="15a6f-121">如果知道所使用的命令类型，通过设置 **CommandType** 属性，可以指示 ADO 直接转到相关代码。</span><span class="sxs-lookup"><span data-stu-id="15a6f-121">If you know what type of command you're using, setting the **CommandType** property instructs ADO to go directly to the relevant code.</span></span> <span data-ttu-id="15a6f-122">如果 **CommandType** 属性与 **CommandText** 属性中的命令类型不匹配，调用 [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 方法时将发生错误。</span><span class="sxs-lookup"><span data-stu-id="15a6f-122">If the **CommandType** property does not match the type of command in the **CommandText** property, an error occurs when you call the [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) method.</span></span>
<span data-ttu-id="15a6f-123">=== ADO 必须进行到提供程序的调用，以确定**CommandText**属性是一个 SQL 语句，因为如果**CommandType**属性值等于**adCmdUnknown** （默认值），您可能会遇到性能降低存储的过程或表名。</span><span class="sxs-lookup"><span data-stu-id="15a6f-123">======= If the **CommandType** property value equals **adCmdUnknown** (the default value), you may experience diminished performance because ADO must make calls to the provider to determine if the **CommandText** property is an SQL statement, a stored procedure, or a table name.</span></span> <span data-ttu-id="15a6f-124">如果知道所使用的命令类型，通过设置 **CommandType** 属性，可以指示 ADO 直接转到相关代码。</span><span class="sxs-lookup"><span data-stu-id="15a6f-124">If you know what type of command you're using, setting the **CommandType** property instructs ADO to go directly to the relevant code.</span></span> <span data-ttu-id="15a6f-125">如果 **CommandType** 属性与 **CommandText** 属性中的命令类型不匹配，调用 [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 方法时将发生错误。</span><span class="sxs-lookup"><span data-stu-id="15a6f-125">If the **CommandType** property does not match the type of command in the **CommandText** property, an error occurs when you call the [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) method.</span></span>
>>>>>>> <span data-ttu-id="15a6f-126">母版</span><span class="sxs-lookup"><span data-stu-id="15a6f-126">master</span></span>

