<!--
 * Tencent is pleased to support the open source community by making
 * 科技内在设计（T-inside） available.
 *
 * Copyright (C) 2021 TID Limited, a DAO.  All rights reserved.
 *
 * 科技内在设计（T-inside） is licensed under the MIT License.
 *
 * License for 科技内在设计（T-inside）:
 *
 *
 * Terms of the MIT License:
 * ---------------------------------------------------
 * Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated
 * documentation files (the "Software"), to deal in the Software without restriction, including without limitation
 * the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and
 * to permit persons to whom the Software is furnished to do so, subject to the following conditions:
 *
 * The above copyright notice and this permission notice shall be included in all copies or substantial portions of
 * the Software.
 *
 * THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT
 * THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
 * AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF
 * CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
 * IN THE SOFTWARE.
-->

<template>
    <section>
        <h2>
            <i href="javascript:void(0)" class="back-icon bk-icon icon-arrows-left" @click="back"></i>
            Info 提示框更多示例
        </h2>
        <div class="example-item">
            <bk-button @click="mountInBody">
                mount in body
            </bk-button>
        </div>
        <div class="example-item">
            <bk-button :theme="'success'" @click="mountInParent" ref="vvv">
                mount in parentNode
            </bk-button>
        </div>
        <div class="example-item">
            <bk-button :theme="'success'" @click="test">
                test
            </bk-button>
        </div>
    </section>
</template>

<script>
    import { bkButton } from '@'
    export default {
        components: {
            bkButton
        },
        data () {
            return {
            }
        },
        methods: {
            back () {
                window.history.go(-1)
            },
            mountInBody () {
                this.$bkInfo({
                    title: 'mount in body'
                })
            },
            mountInParent () {
                this.$bkInfo({
                    title: 'mount in parentNode',
                    // container: document.querySelectorAll('.example-item')[1]
                    container: this.$refs.vvv
                })
            },
            test () {
                // const h = this.$createElement
                this.$bkInfo({
                    title: '支持VNode的提示框',
                    subHeader: 'subHeader',
                    subTitle: 'sdsdssd'
                })
            }
        }
    }
</script>
