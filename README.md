import { defineStore } from 'pinia'

export const useUserStore = defineStore('user', {
  state: () => ({
    token: localStorage.getItem('token') || '',
    user: null
  }),
  actions: {
    setToken(token) {
      this.token = token
      localStorage.setItem('token', token)
    },
    clearToken() {
      this.token = ''
      localStorage.removeItem('token')
    },
    setUser(userData) {
      this.user = userData
    }
  }
})
