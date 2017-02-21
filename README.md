# HW4Testing{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# CPE-341, Quiz 2/2015\n",
    "# Question Set D\n",
    "\n",
    "- Iteration Design Pattern : List, Dictionary\n",
    "- Using Class `Card` in a List"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 44,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "ename": "ImportError",
     "evalue": "No module named 'load_style'",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[1;31mImportError\u001b[0m                               Traceback (most recent call last)",
      "\u001b[1;32m<ipython-input-44-78e4da72be5d>\u001b[0m in \u001b[0;36m<module>\u001b[1;34m()\u001b[0m\n\u001b[1;32m----> 1\u001b[1;33m \u001b[0mget_ipython\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mmagic\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;34m'reload_ext load_style'\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m      2\u001b[0m \u001b[0mget_ipython\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mmagic\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;34m'load_style talk.css'\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;32m/home/ubuntu/workspace/run/envs/py34/lib/python3.4/site-packages/IPython/core/interactiveshell.py\u001b[0m in \u001b[0;36mmagic\u001b[1;34m(self, arg_s)\u001b[0m\n\u001b[0;32m   2161\u001b[0m         \u001b[0mmagic_name\u001b[0m\u001b[1;33m,\u001b[0m \u001b[0m_\u001b[0m\u001b[1;33m,\u001b[0m \u001b[0mmagic_arg_s\u001b[0m \u001b[1;33m=\u001b[0m \u001b[0marg_s\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mpartition\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;34m' '\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m   2162\u001b[0m         \u001b[0mmagic_name\u001b[0m \u001b[1;33m=\u001b[0m \u001b[0mmagic_name\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mlstrip\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mprefilter\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mESC_MAGIC\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m-> 2163\u001b[1;33m         \u001b[1;32mreturn\u001b[0m \u001b[0mself\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mrun_line_magic\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mmagic_name\u001b[0m\u001b[1;33m,\u001b[0m \u001b[0mmagic_arg_s\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m   2164\u001b[0m \u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m   2165\u001b[0m     \u001b[1;31m#-------------------------------------------------------------------------\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;32m/home/ubuntu/workspace/run/envs/py34/lib/python3.4/site-packages/IPython/core/interactiveshell.py\u001b[0m in \u001b[0;36mrun_line_magic\u001b[1;34m(self, magic_name, line)\u001b[0m\n\u001b[0;32m   2082\u001b[0m                 \u001b[0mkwargs\u001b[0m\u001b[1;33m[\u001b[0m\u001b[1;34m'local_ns'\u001b[0m\u001b[1;33m]\u001b[0m \u001b[1;33m=\u001b[0m \u001b[0msys\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0m_getframe\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mstack_depth\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mf_locals\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m   2083\u001b[0m             \u001b[1;32mwith\u001b[0m \u001b[0mself\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mbuiltin_trap\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m-> 2084\u001b[1;33m                 \u001b[0mresult\u001b[0m \u001b[1;33m=\u001b[0m \u001b[0mfn\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;33m*\u001b[0m\u001b[0margs\u001b[0m\u001b[1;33m,\u001b[0m\u001b[1;33m**\u001b[0m\u001b[0mkwargs\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m   2085\u001b[0m             \u001b[1;32mreturn\u001b[0m \u001b[0mresult\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m   2086\u001b[0m \u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;32m<decorator-gen-66>\u001b[0m in \u001b[0;36mreload_ext\u001b[1;34m(self, module_str)\u001b[0m\n",
      "\u001b[1;32m/home/ubuntu/workspace/run/envs/py34/lib/python3.4/site-packages/IPython/core/magic.py\u001b[0m in \u001b[0;36m<lambda>\u001b[1;34m(f, *a, **k)\u001b[0m\n\u001b[0;32m    191\u001b[0m     \u001b[1;31m# but it's overkill for just that one bit of state.\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m    192\u001b[0m     \u001b[1;32mdef\u001b[0m \u001b[0mmagic_deco\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0marg\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m--> 193\u001b[1;33m         \u001b[0mcall\u001b[0m \u001b[1;33m=\u001b[0m \u001b[1;32mlambda\u001b[0m \u001b[0mf\u001b[0m\u001b[1;33m,\u001b[0m \u001b[1;33m*\u001b[0m\u001b[0ma\u001b[0m\u001b[1;33m,\u001b[0m \u001b[1;33m**\u001b[0m\u001b[0mk\u001b[0m\u001b[1;33m:\u001b[0m \u001b[0mf\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;33m*\u001b[0m\u001b[0ma\u001b[0m\u001b[1;33m,\u001b[0m \u001b[1;33m**\u001b[0m\u001b[0mk\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m    194\u001b[0m \u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m    195\u001b[0m         \u001b[1;32mif\u001b[0m \u001b[0mcallable\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0marg\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;32m/home/ubuntu/workspace/run/envs/py34/lib/python3.4/site-packages/IPython/core/magics/extension.py\u001b[0m in \u001b[0;36mreload_ext\u001b[1;34m(self, module_str)\u001b[0m\n\u001b[0;32m     94\u001b[0m         \u001b[1;32mif\u001b[0m \u001b[1;32mnot\u001b[0m \u001b[0mmodule_str\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m     95\u001b[0m             \u001b[1;32mraise\u001b[0m \u001b[0mUsageError\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;34m'Missing module name.'\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m---> 96\u001b[1;33m         \u001b[0mself\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mshell\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mextension_manager\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mreload_extension\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mmodule_str\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m",
      "\u001b[1;32m/home/ubuntu/workspace/run/envs/py34/lib/python3.4/site-packages/IPython/core/extensions.py\u001b[0m in \u001b[0;36mreload_extension\u001b[1;34m(self, module_str)\u001b[0m\n\u001b[0;32m    127\u001b[0m                 \u001b[0mself\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mloaded\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0madd\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mmodule_str\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m    128\u001b[0m         \u001b[1;32melse\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m--> 129\u001b[1;33m             \u001b[0mself\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mload_extension\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mmodule_str\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m    130\u001b[0m \u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m    131\u001b[0m     \u001b[1;32mdef\u001b[0m \u001b[0m_call_load_ipython_extension\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mself\u001b[0m\u001b[1;33m,\u001b[0m \u001b[0mmod\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;32m/home/ubuntu/workspace/run/envs/py34/lib/python3.4/site-packages/IPython/core/extensions.py\u001b[0m in \u001b[0;36mload_extension\u001b[1;34m(self, module_str)\u001b[0m\n\u001b[0;32m     82\u001b[0m             \u001b[1;32mif\u001b[0m \u001b[0mmodule_str\u001b[0m \u001b[1;32mnot\u001b[0m \u001b[1;32min\u001b[0m \u001b[0msys\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mmodules\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m     83\u001b[0m                 \u001b[1;32mwith\u001b[0m \u001b[0mprepended_to_syspath\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mself\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mipython_extension_dir\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m---> 84\u001b[1;33m                     \u001b[0m__import__\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mmodule_str\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m     85\u001b[0m             \u001b[0mmod\u001b[0m \u001b[1;33m=\u001b[0m \u001b[0msys\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mmodules\u001b[0m\u001b[1;33m[\u001b[0m\u001b[0mmodule_str\u001b[0m\u001b[1;33m]\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m     86\u001b[0m             \u001b[1;32mif\u001b[0m \u001b[0mself\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0m_call_load_ipython_extension\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mmod\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;31mImportError\u001b[0m: No module named 'load_style'"
     ]
    }
   ],
   "source": [
    "%reload_ext load_style\n",
    "%load_style talk.css"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'2017-02-10T02:44:09.306941'"
      ]
     },
     "execution_count": 3,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "## 57113023-6\n",
    "##wararwit mankran\n",
    "##\n",
    "## คลิก Run cell นี้เพียงครั้งเดียว\n",
    "##\n",
    "##\n",
    "import datetime\n",
    "datetime.datetime.now().isoformat()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Question 1 ( @2 pt x 2 = 4 pts )\n",
    "\n",
    "### Q1.a \n",
    "จงเขียนคำสั่ง เพื่อพิมพ์ค่าตัวเลขจาก list `mycoins` ที่ index ที่กำหนดให้"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 45,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "## ไม่แก้ไขข้อมูลใน cell นี้\n",
    "\n",
    "mycoins = [12, 4, 10, 1, 6, 18, 19, 4]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 46,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "19\n"
     ]
    }
   ],
   "source": [
    "## ANSWER Q1.a\n",
    "##\n",
    "index = 6\n",
    "\n",
    "\n",
    "\n",
    "print(mycoins[index])\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Q1.b \n",
    "จงเขียนคำสั่ง เพื่อพิมพ์ตัวเลขที่มีค่า ***น้อยกว่า*** 10 จาก **list** `mycoins` ในข้อ (1.a)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 47,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "4\n",
      "1\n",
      "6\n"
     ]
    }
   ],
   "source": [
    "## ANSWER Q1.b\n",
    "##\n",
    "\n",
    "for x in range(0, 7):\n",
    "     if mycoins[x] <10:\n",
    "        print(mycoins[x])\n",
    "    \n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Question 2 ( @3 pts x 4 = 12 pts )\n",
    "\n",
    "### Q2.a \n",
    "จงสร้าง **list** เพื่อเก็บข้อมูลตัวเลขคู่ $ 2, 4, 6, ... , 28, 30, 32 $   โดยใข้ `range`"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 48,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "[2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32]\n"
     ]
    }
   ],
   "source": [
    "## ANSWER Q2.a\n",
    "##\n",
    "\n",
    "\n",
    "mylist=list(range(2,34,2))\n",
    "print(mylist)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Q2.b \n",
    "จงสร้าง **list** เพื่อเก็บ**ตัวเลขสุ่ม** ในช่วง 1-99 จำนวน 4 ตัวเลข โดยใข้ฟังก์ชั่น `randint` จากไลบรารี `random`"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 65,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "## ANSWER Q2.b\n",
    "## \n",
    "## \n",
    "\n",
    "from random import randint\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 50,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "list2=[]\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 51,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "[83, 30, 93, 61] "
     ]
    }
   ],
   "source": [
    "for i in range(0,4):\n",
    "    x = random.randint(0, 99)\n",
    "    list2.append(x)\n",
    "print(list2,end=\" \")"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Q2.c \n",
    "จงเขียน `def` ชื่อ `sum_of_sqrt` สำหรับหาผลรวมของ square root ของตัวเลขใน **list** ที่เป็น argument  \n",
    "\n",
    "เช่น เมื่อเรียกใช้ `sum_of_sqrt([1,2,3,4,5,6,7,8,9])` จะได้ผลลัพธ์เป็นดังนี้\n",
    "\n",
    "$$\\sqrt{1}  + \\sqrt{2} + \\sqrt{3} +  ...  + \\sqrt{7} + \\sqrt{8} + \\sqrt{9} = 19.30600052603572 $$"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 66,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "from math import sqrt\n",
    "\n",
    "def sum_of_sqrt(number_list):\n",
    "    m=0\n",
    "    for x in number_list:\n",
    "        m = m+math.sqrt(x)\n",
    "    return m"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 53,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]\n"
     ]
    },
    {
     "data": {
      "text/plain": [
       "19.30600052603572"
      ]
     },
     "execution_count": 53,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "## Test sum_of_sqrt()\n",
    "nums = [i for i in range(10) ]\n",
    "\n",
    "print(nums)\n",
    "sum_of_sqrt(nums)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 54,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "[100, 104, 108, 112, 116, 120]\n"
     ]
    },
    {
     "data": {
      "text/plain": [
       "62.89812988122953"
      ]
     },
     "execution_count": 54,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "## Test sum_of_sqrt() again \n",
    "nums = [100, 104, 108, 112, 116, 120]\n",
    "\n",
    "print(nums)\n",
    "sum_of_sqrt(nums)\n",
    "\n",
    "# should print out:\n",
    "# 62.89812988122953"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Q2.d \n",
    "จงหา**ค่าเฉลี่ย**ของตัวเลขใน **list** ต่อไปนี้ แล้วเก็บไว้ที่ตัวแปรชื่อ `avg_` โดยใข้ฟังก์ชั่น `sum`, `len` \n",
    "\n",
    "```\n",
    "myTest = [200, 265, 228, 202, 235, 284]\n",
    "```"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 67,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "# ANSWER Q2.d\n",
    "##\n",
    "##\n",
    "\n",
    "myTest = [200, 265, 228, 202, 235, 284]\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 72,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "235.66666666666666\n"
     ]
    }
   ],
   "source": [
    "def avg_(num):\n",
    "    print (sum(num)/len(num))\n",
    "    \n",
    "avg_(myTest)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Question 3 ( @6 pts x 2 = 12 pts )\n",
    "\n",
    "### Q3.a \n",
    "กำหนดให้ **dict** `๋JP_COINS` เก็บค่าเงินของเหรียญญี่ปุ่น (เงินเยน ¥) 6 ชนิด (ใช้ใน Q3.b)\n",
    "\n",
    "จงหาจำนวนเหรียญใน list `piggy` ซึ่งเป็นกระปุกเงินเก็บเหรียญ โดยผลลัพธ์เก็บค่าไว้ที่ตัวแปร `count` "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 57,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "## ไม่แก้ไขข้อมูลใน cell นี้\n",
    "\n",
    "JP_COINS = { \"1Y\": 1, \"5Y\": 5, \"10Y\": 10, \"50Y\": 50, \"100Y\": 100, \"500Y\": 500 }\n",
    "\n",
    "## piggy keeps the number of Japanese ¥ coins \n",
    "piggy = { \"500Y\":2, \"1Y\":8, \"100Y\":4, \"10Y\":24, \"50Y\":2 }"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 74,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "40\n"
     ]
    }
   ],
   "source": [
    "## ANSWER Q3.a\n",
    "##\n",
    "\n",
    "count = 0\n",
    "#------- add your code here\n",
    "for i in piggy:\n",
    "    count = count+piggy[i]\n",
    "\n",
    "print (count)\n",
    "\n",
    "\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 59,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "40\n"
     ]
    }
   ],
   "source": [
    "print(count)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {
    "collapsed": true
   },
   "source": [
    "### Q3.b\n",
    "จงหามูลค่าของเงินทั้งหมดใน list `piggy` (หน่วย: เยน)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 75,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "1748.0\n"
     ]
    }
   ],
   "source": [
    "## ANSWER Q3.b\n",
    "##\n",
    "\n",
    "total = 0.\n",
    "#------ add your code here\n",
    "for i in piggy:\n",
    "   total =total + JP_COINS[i]*piggy[i]\n",
    "\n",
    "print (total)\n",
    "\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "0.0\n"
     ]
    }
   ],
   "source": [
    "print(total)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Question 4 ( @6 pts x 2 = 12 pts )\n",
    "\n",
    "### Q4.a \n",
    "จาก class `Card` ซึ่งแทนไพ่แต่ละใบ จงสร้างไพ่ 4 ใบที่ไม่ซ้ำกัน เก็บไว้ใน list ชื่อ `my_cards` แล้วหาค่าผลรวมของหน้าไพ่ เก็บผลลัพธ์ที่ตัวแปร `my_points`\n",
    "\n",
    "ในที่นี้ ให้คิดหน้าไพ่ ตาม rank ที่กำหนดใน dict `CARD_VALUE` \n",
    "เช่น ไพ่ `2` มีค่า `2`, `3` มีค่า 3, .... ไพ่ `T` (หรือเลข 10) มีค่า 10, `J` มีค่า 11, ..., ไพ่ `A` มีค่า 14 "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 28,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "## ไม่แก้ไขข้อมูลใน cell นี้\n",
    "CARD_SUIT = \"cdhs\"             # Club, Diamond, Heart, Spade\n",
    "CARD_RANK = \"--23456789TJQKA\"  # index 0-1 not used\n",
    "CARD_VALUE = {\n",
    "    '2':2, '3':3, '4':4,  '5':5,  '6':6,  '7':7,\n",
    "    '8':8, '9':9, 'T':10, 'J':11, 'Q':12, 'K':13, 'A':14\n",
    "}\n",
    "\n",
    "class Card(object):     \n",
    "    def __init__(self, face):\n",
    "        self.__face = face\n",
    "        \n",
    "    @property\n",
    "    def face(self):\n",
    "        return self.__face\n",
    "        \n",
    "    @property\n",
    "    def suit(self):\n",
    "        card_suit = self.__face[0]\n",
    "        return card_suit\n",
    "\n",
    "    @property\n",
    "    def rank(self):\n",
    "        card_rank = self.__face[1]\n",
    "        return card_rank        "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 61,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "c 2 c2\n"
     ]
    }
   ],
   "source": [
    "## ตัวอย่างการสร้่้างไพ่ 1 ใบ\n",
    "c1 = Card('c2')\n",
    "print(c1.suit, c1.rank,c1.face)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 62,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "12\n"
     ]
    }
   ],
   "source": [
    "## example: look up for the value of a card\n",
    "c2 = Card('sQ')\n",
    "print( CARD_VALUE[ c2.rank ] ) "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 33,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<__main__.Card at 0x7f63840b0eb8>"
      ]
     },
     "execution_count": 33,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "c3 = Card('dT')\n",
    "c3"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 34,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "## ANSWER Q4.a\n",
    "##\n",
    "## สร้างไพ่ 4 ใบที่ไม่ซ้ำกัน เก็บไว้ใน list ชื่อ my_cards \n",
    "## แล้วหาค่าผลรวมของหน้าไพ่ เก็บผลลัพธ์ที่ตัวแปร my_points\n",
    "##\n",
    "\n",
    "# create 4 cards in  my_cards\n",
    "my_cards = []  \n",
    "\n",
    "my_points = 0\n",
    "#--------- add your code here\n",
    "cards=['d2', 'sQ', 'cA', 'h8']\n",
    "cards2=['d3', 'h2',  'c4', 'cA']\n",
    "for c2 in cards2:\n",
    "    my_cards.append(Card(c2))\n",
    "    my_points += CARD_VALUE[ Card(c2).rank ]\n",
    "\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": 35,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "My cards: d3 h2 c4 cA. Total value: 23.\n"
     ]
    }
   ],
   "source": [
    "# Run this to print the faces of 4 cards, and my_points\n",
    "card_faces_str = \"My cards:\"\n",
    "for c in my_cards:\n",
    "    card_faces_str += \" \" + c.face\n",
    "    \n",
    "print(\"{}. Total value: {}.\".format(card_faces_str, my_points))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 36,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "# Test 4 cards of 'd2', 'sQ', 'cA', 'h8'\n",
    "#....Total value is 36\n",
    "\n",
    "# Test 4 cards of 'd3', 'h2',  'c4', 'cA'\n",
    "#....Total value is 23"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Q4.b \n",
    "จงปรับปรุุง def `printCards` เพื่อพิมพ์หน้าไพ่, จำนวนไพ่ และค่าผลรวมของหน้าไพ่ทั้งหมดที่อยู่ใน list `card_list` \n",
    "\n",
    "**ตัวอย่างผลลัพธ์**\n",
    "```\n",
    "---------------- Cards ----------------\n",
    "Cards : ['d2', 'sQ', 'cA', 'h8']\n",
    "Count : 4\n",
    "Value : 36\n",
    "```"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 85,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "## ANSWER Q3.b\n",
    "## พิมพ์หน้าไพ่, จำนวนไพ่ และค่าผลรวมของหน้าไพ่ทั้งหมดที่อยู่ใน card_list\n",
    "##\n",
    "\n",
    "def printCards( card_list ):\n",
    "    total_value = 0 \n",
    "    count = 0\n",
    "    \n",
    "    for c2 in card_list:\n",
    "        total_value += CARD_VALUE[ c2.rank ]\n",
    "    count = len(card_list)\n",
    "    \n",
    "    card_faces_str = [c.face for c in card_list]        \n",
    "    print(\"---------------- Cards ----------------\")\n",
    "    print(\"Cards : {}\".format( card_faces_str ))\n",
    "    print(\"Count : {}\".format( count ))\n",
    "    print(\"Value : {}\".format( total_value ))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 86,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "---------------- Cards ----------------\n",
      "Cards : ['d3', 'h2', 'c4', 'cA']\n",
      "Count : 4\n",
      "Value : 23\n"
     ]
    }
   ],
   "source": [
    "#--- Test the def printCoins ---\n",
    "printCards( my_cards )\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": 43,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'2017-02-20T07:55:52.302533'"
      ]
     },
     "execution_count": 43,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "import datetime\n",
    "datetime.datetime.now().isoformat()\n",
    "##\n",
    "## 57113023-6\n",
    "##wararwit mankran\n",
    "## แล้วคลิก Run cell ครั้งเดียว เมื่อส่งงาน"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## end of IPynb"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.4.4"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 0
}
