<template>
  <v-card>
    <v-container
      fluid
      style="min-height: 0;"
      grid-list-lg
      >
      <v-flex xs12 sm6 offset-sm3>
        <v-layout wrap column>
          <v-flex>
            <v-card class="invoice-container">
              <div ref="invoiceData">
                <v-flex>
                  <h3 class="label-service">
                    {{ serviceName }}
                  </h3>
                  <div>
                    <qriously v-model="qrValue" :size="qrSize" :foreground="qrColor"/>
                  </div>
                  <table border="0" class="table__list">
                      <tr>
                        <td width="20%" class="table__key">コイン数</td>
                        <td width="80%" class="table__value">{{ price }}</td>
                      </tr>
                      <tr>
                        <td width="20%" class="table__key">利用条件</td>
                        <td width="80%" class="table__text">{{ termsOfUse }}</td>
                      </tr>
                  </table>
                </v-flex>
                <v-flex>
                  <p class="label-howtoreceive">{{ howtoReceive }}</p>
                  <span class="label-event">{{ eventName }}</span>
                </v-flex>
              </div>
            </v-card>
          </v-flex>
        </v-layout>
      </v-flex>
    </v-container>
  </v-card>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class InvoiceCode extends Vue {
  private serviceName: string = 'ケンタッキー'
  private price: string = '100 marine'
  private termsOfUse: string = '１品以上ご注文いただいた方'
  private howtoReceive: string = 'お越しの際にアプリを提示してください'
  private eventName: string = '居酒屋 宮古島'
  private qrValue: string = '{"value":{"type":0,"id":"aiueo"}}'
  private qrSize: number = 300

  // QRの色を設定
  private qrColor: string = 'white'
}
</script>

<!-- デザイン -->
<style lang="stylus" scoped>
@import '../assets/main.styl'

p
  font-size 14px

// 請求書の背景
.invoice-container
  background blue

// 請求書名
.label-service
  color white
  margin 10px

.table
  &__list
    margin 0 auto

  // 左のコメント
  &__key
    font-size 14px
    text-align center
    color white
    padding 8px 2px

  // コイン
  &__value
    font-size 20px
    font-weight bold
    text-align center
    color white
    padding 8px

  // 利用条件
  &__text
    font-size 14px
    text-align center
    color white
    padding 8px

// お受け取り
.label-howtoreceive
  color white

// 加盟店
.label-event
  display block
  font-size 14px
  text-align right 
  color white
</style>
